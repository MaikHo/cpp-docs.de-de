---
title: Die Hilfsfunktion
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
ms.openlocfilehash: 3ad193d0101507f43145c6af9f8e6200ab6fcdb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317665"
---
# <a name="understanding-the-helper-function"></a>Die Hilfsfunktion

Die Hilfsfunktion für das verzögerte Laden Linker unterstützt wird, was tatsächlich die DLL zur Laufzeit geladen. Sie können die Hilfsfunktion, um dessen Verhalten anpassen, indem Sie eine eigene Funktion geschrieben, und dessen Verknüpfung mit Ihrem Programm verwenden, statt mit der Hilfsfunktion für das angegebene in "delayimp.lib" ändern. Eine Hilfsfunktion dient alle verzögert geladene DLLs.

Sie können Ihre eigene Version der Hilfsfunktion bereitstellen, wenn bestimmte Verarbeitung basierend auf den Namen der DLL oder importiert werden sollen.

Die Hilfsfunktion führt folgende Aktionen aus:

- Überprüft das gespeicherte Handle in die Bibliothek aus, um festzustellen, ob sie bereits geladen wurde

- Aufrufe **LoadLibrary** Laden der DLL versucht.

- Aufrufe **GetProcAddress** versucht, die Adresse der Prozedur abrufen

- Zurückgegeben wird, um das von Import verzögern Thunk, um die neu geladenen Einstiegspunkt aufrufen

Die Hilfsfunktion kann ein Benachrichtigungshook in Ihrem Programm nach jedem der folgenden Aktionen erreichen:

- Wenn die Hilfsfunktion gestartet wird

- Kurz bevor **LoadLibrary** in der Hilfsfunktion aufgerufen wird

- Kurz bevor **GetProcAddress** in der Hilfsfunktion aufgerufen wird

- Wenn der Aufruf von **LoadLibrary** Fehler in der Hilfsfunktion

- Wenn der Aufruf von **GetProcAddress** Fehler in der Hilfsfunktion

- Nachdem das Hilfsprogramm Funktion erfolgt Verarbeitung

Jede dieser Punkte verknüpfen kann einen Wert, der die normale Verarbeitung von die Hilfsroutine hat, mit Ausnahme der Rückgabe an den Import verzögert geladenen Thunk dahingehend geändert, wird zurückgegeben.

Der Hilfscode standardmäßigen finden Sie in Delayhlp.cpp und Delayimp.h (in Vc\include) und ist in "delayimp.lib" (in Vc\lib) kompiliert. Sie müssen diese Bibliothek in den Kompilierungen eingeschlossen werden sollen, wenn Sie eine eigene Hilfsfunktion schreiben.

Die folgenden Themen beschreiben die Hilfsfunktion:

- [Änderungen an der Hilfsfunktion für das verzögerte Laden von DLLs seit Visual C++ 6.0](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [Aufrufkonventionen, Parameter und Rückgabetyp](calling-conventions-parameters-and-return-type.md)

- [Struktur- und Konstantendefinitionen](structure-and-constant-definitions.md)

- [Berechnen der erforderlichen Werte](calculating-necessary-values.md)

- [Entladen einer verzögert geladenen DLL](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>Siehe auch

[Linkerunterstützung für verzögertes Laden von DLLs](linker-support-for-delay-loaded-dlls.md)
