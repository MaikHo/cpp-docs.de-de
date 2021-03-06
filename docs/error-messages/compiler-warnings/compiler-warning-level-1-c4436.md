---
title: Compilerwarnung (Stufe 1) C4436
ms.date: 11/04/2016
f1_keywords:
- C4436
helpviewer_keywords:
- C4436
ms.assetid: 2b54a1fc-c9c6-4cc9-90be-faa44fc715d5
ms.openlocfilehash: 6a15220cb02a48fb11936b69e5830412f1221108
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230674"
---
# <a name="compiler-warning-level-1-c4436"></a>Compilerwarnung (Stufe 1) C4436

die dynamic_cast von der virtuellen Basis "Class1" zu "Klasse2" im Konstruktor oder Dekonstruktor schlägt möglicherweise mit der teilweise konstruierten Objekt Kompilierung mit "/vd2" fehl oder definiert "Klasse2" mit #Pragma vtordisp (2).

Der Compiler hat einen- **`dynamic_cast`** Vorgang mit den folgenden Merkmalen gefunden.

- Die Umwandlung erfolgt von einem Basisklassen Zeiger auf einen abgeleiteten Klassen Zeiger.

- Die abgeleitete Klasse erbt virtuell die Basisklasse.

- Die abgeleitete Klasse verfügt über kein `vtordisp` Feld für die virtuelle Basis.

- Die Umwandlung befindet sich in einem Konstruktor oder Dekonstruktor der abgeleiteten Klasse oder in einer Klasse, die weiter von der abgeleiteten Klasse erbt.

Die Warnung gibt **`dynamic_cast`** an, dass möglicherweise nicht ordnungsgemäß ausgeführt wird, wenn es auf einem teilweise konstruierten Objekt ausgeführt wird.  Dies ist der Fall, wenn der abgeleitete Konstruktor/Dekonstruktor für ein untergeordnetes Objekt eines weiteren abgeleiteten Objekts ausgeführt wird.  Wenn die abgeleitete Klasse, die in der Warnung benannt ist, nie weiter abgeleitet wird, kann die Warnung ignoriert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4436 generiert und das Code Generierungs Problem veranschaulicht, das im fehlenden `vtordisp` Feld auftritt.

```cpp
// C4436.cpp
// To see the warning and runtime assert, compile with: /W1
// To eliminate the warning and assert, compile with: /W1 /vd2
//       or compile with: /W1 /DFIX
#include <cassert>

struct A
{
public:
    virtual ~A() {}
};

#if defined(FIX)
#pragma vtordisp(push, 2)
#endif
struct B : virtual A
{
    B()
    {
        A* a = static_cast<A*>(this);
        B* b = dynamic_cast<B*>(a);     // C4436
        assert(this == b);              // assert unless compiled with /vd2
    }
};
#if defined(FIX)
#pragma vtordisp(pop)
#endif

struct C : B
{
    int i;
};

int main()
{
    C c;
}
```

## <a name="see-also"></a>Weitere Informationen

[dynamic_cast-Operator](../../cpp/dynamic-cast-operator.md)<br/>
[vtordisp](../../preprocessor/vtordisp.md)<br/>
[Compilerwarnung (Stufe 4) C4437](../../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md)
