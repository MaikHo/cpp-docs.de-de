---
title: Quellcodeorganisation (C++-Vorlagen)
ms.date: 04/22/2019
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
ms.openlocfilehash: ecd682056f27200ae31c27295c1aabaf72c74a18
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186112"
---
# <a name="source-code-organization-c-templates"></a>Quellcodeorganisation (C++-Vorlagen)

Wenn Sie eine Klassenvorlage definieren, müssen Sie den Quellcode so organisieren, dass die Memberdefinitionen für den Compiler sichtbar sind, wenn dieser sie benötigt. Sie können zwischen einem *Einschlussmodell* und einem Modell der *expliziten Instanziierung* wählen. Im Inklusions Modell schließen Sie die Element Definitionen in jede Datei ein, die eine Vorlage verwendet. Diese Vorgehensweise ist die einfachsten und bietet maximale Flexibilität im Hinblick auf die konkreten Typen, die mit Ihrer Vorlage verwendet werden können. Der Nachteil ist, dass sich die Kompilierungszeiten verlängern können. Dies kann erhebliche Auswirkungen haben, wenn ein Projekt und/oder die eingeschlossenen Dateien selbst sehr groß sind. Beim Ansatz der expliziten Instanziierung instanziiert die Vorlage selbst konkrete Klassen oder Klassenmember für bestimmte Typen.  Dies kann die Kompilierung beschleunigen, beschränkt aber die Verwendung auf diejenigen Klassen, die bei der Vorlagenimplementierung im Voraus aktiviert wurden. Im Allgemeinen empfehlen wir das Einschlussmodell, es sei denn, dass die Kompilierungszeiten ein Problem darstellen.

## <a name="background"></a>Hintergrund

Vorlagen sind keine normalen Klassen in dem Sinne, dass der Compiler keinen Objektcode für eine Vorlage oder einen der darin enthaltenen Member generiert. Bis die Vorlage mit konkreten Typen instanziiert wird, gibt es nichts zu generieren. Wenn der Compiler eine Vorlageninstanziierung wie `MyClass<int> mc;` findet, aber noch keine Klasse mit dieser Signatur vorhanden ist, generiert der Compiler eine neue Klasse. Er versucht auch, Code für alle verwendeten Memberfunktionen zu generieren. Wenn sich diese Definitionen in einer Datei befinden, die nicht direkt oder indirekt per „#include“ eingeschlossen ist, kann der Compiler die Definitionen in der kompilierten .cpp-Datei nicht finden.  Aus Sicht des Compilers ist dies nicht unbedingt ein Fehler, weil die Funktionen in einer anderen Übersetzungseinheit definiert sein können – in diesem Fall findet der Linker sie.  Wenn der Linker diesen Code nicht findet, gibt er einen *nicht aufgelösten internen* Fehler aus.

## <a name="the-inclusion-model"></a>Das Einschlussmodell

Die einfachste und gängigste Art und Weise, Vorlagendefinitionen in einer Übersetzungseinheit sichtbar zu machen, besteht darin, die Definitionen in der Headerdatei selbst zu platzieren.  Jede .cpp-Datei, die die Vorlage verwendet, muss einfach nur den Header per „#include“ einschließen. Dies ist das Verfahren, das in der Standardbibliothek zur Anwendung kommt.

```cpp
#ifndef MYARRAY
#define MYARRAY
#include <iostream>

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    // Full definitions:
    MyArray(){}
    void Print()
    {
        for (const auto v : arr)
        {
            std::cout << v << " , ";
        }
    }

    T& operator[](int i)
   {
       return arr[i];
   }
};
#endif
```

Bei diesem Ansatz hat der Compiler Zugriff auf die vollständige Vorlagen Definition und kann bei Bedarf Vorlagen für jeden beliebigen Typ instanziieren. Das ist einfach und relativ einfach zu verwalten. Das Einschlussmodell weist jedoch in Sachen Kompilierungszeit einen Nachteil auf. Dieser Nachteil kann in großen Programmen sehr schwer wiegen, insbesondere dann, wenn der Vorlagenheader selbst andere Header per „#include“ einschließt. Jede *`.cpp`* Datei, die den Header #includes, erhält eine eigene Kopie der Funktions Vorlagen und aller Definitionen. Der Linker ist im Allgemeinen in der Lage, dies zu verarbeiten, sodass Sie nicht am Ende mit mehreren Definitionen für eine Funktion dastehen. Für diese Verarbeitung braucht er allerdings Zeit. In kleineren Programmen ist diese zusätzliche Kompilierungszeit wahrscheinlich nicht relevant.

## <a name="the-explicit-instantiation-model"></a>Das Modell der expliziten Instanziierung

Wenn das Inklusions Modell für Ihr Projekt nicht praktikabel ist und Sie definitiv den Satz von Typen kennen, der zum Instanziieren einer Vorlage verwendet wird, können Sie den Vorlagen Code in eine *`.h`* -und- *`.cpp`* Datei aufteilen und in der *`.cpp`* Datei die Vorlagen explizit instanziieren. Damit wird Objektcode generiert, den der Compiler sieht, wenn Benutzerinstanziierungen auftreten.

Sie erstellen eine explizite Instanziierung, indem Sie die Schlüsselwortvorlage gefolgt von der Signatur der Entität verwenden, die Sie instanziieren möchten. Hierbei kann es sich um einen Typ oder einen Member handeln. Wenn Sie explizit einen Typ instanziieren, werden alle Member instanziiert.

```cpp
template MyArray<double, 5>;
```

```cpp
//MyArray.h
#ifndef MYARRAY
#define MYARRAY

template<typename T, size_t N>
class MyArray
{
    T arr[N];
public:
    MyArray();
    void Print();
    T& operator[](int i);
};
#endif

//MyArray.cpp
#include <iostream>
#include "MyArray.h"

using namespace std;

template<typename T, size_t N>
MyArray<T,N>::MyArray(){}

template<typename T, size_t N>
void MyArray<T,N>::Print()
{
    for (const auto v : arr)
    {
        cout << v << "'";
    }
    cout << endl;
}

template MyArray<double, 5>;template MyArray<string, 5>;
```

Im vorherigen Beispiel befinden sich die expliziten Instanziierungen am Ende der .cpp-Datei. Ein `MyArray` kann nur für-oder-Typen verwendet werden **`double`** `String` .

> [!NOTE]
> In c++ 11 **`export`** wurde das Schlüsselwort im Kontext von Vorlagen Definitionen als veraltet markiert. In der Praxis hat dies wenig Auswirkungen, da die meisten Compiler dieses Schlüsselwort nie unterstützt haben.
