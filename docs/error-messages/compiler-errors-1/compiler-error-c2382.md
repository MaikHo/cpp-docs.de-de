---
title: Compilerfehler C2382
ms.date: 11/04/2016
f1_keywords:
- C2382
helpviewer_keywords:
- C2382
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
ms.openlocfilehash: 8b623d292998960052ff5d6978d8c12ae7f3fb32
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745368"
---
# <a name="compiler-error-c2382"></a>Compilerfehler C2382

„function“: Neudefinition; unterschiedliche Ausnahmespezifikationen

Unter [/Za](../../build/reference/za-ze-disable-language-extensions.md)zeigt dieser Fehler an, dass eine Funktionsüberladung nur auf für die [Ausnahmespezifikation](../../cpp/exception-specifications-throw-cpp.md)versucht wurde.

Im folgenden Beispiel wird C2382 generiert:

```cpp
// C2382.cpp
// compile with: /Za /c
void f1(void) throw(int) {}
void f1(void) throw(char) {}   // C2382
void f2(void) throw(char) {}   // OK
```
