---
title: Compilerfehler C3510
ms.date: 11/04/2016
f1_keywords:
- C3510
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
ms.openlocfilehash: 3f9dea77b739aa59474e60cf852fff2577ab6ba9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753626"
---
# <a name="compiler-error-c3510"></a>Compilerfehler C3510

die abhängige Typbibliothek "Type_lib" wurde nicht gefunden.

[no_registry](../../preprocessor/no-registry.md) und [auto_search](../../preprocessor/auto-search.md) wurden an `#import`, aber der Compiler konnte eine referenzierte Typbibliothek nicht finden.

Stellen Sie sicher, dass alle Typbibliotheken und referenzierten Typbibliotheken für den Compiler verfügbar sind, um diesen Fehler zu beheben.

Im folgenden Beispiel wird C3510 generiert:

Angenommen, die folgenden beiden Typbibliotheken wurden erstellt, und C3510a. tlb wurde gelöscht oder ist nicht im Pfad.

```
// C3510a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C3510aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]
   enum E_C3510
   {
      one, two, three
   };
};
```

Und dann der Quellcode für die zweite Typbibliothek:

```
// C3510b.idl
// post-build command: del /f C3510a.tlb
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
library C3510bLib
{
   importlib ("C3510a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
   struct S_C3510 {
      enum E_C3510 e;
   };
};
```

Und dann der Client Code:

```cpp
// C3510.cpp
#import "c3510b.tlb" no_registry auto_search   // C3510
int main() {
   C3510aLib::S_C4336 ccc;
}
```
