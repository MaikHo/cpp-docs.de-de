---
title: Compilerfehler C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: 030a6acb19c0907956d2a5b833b683821591e5c5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758111"
---
# <a name="compiler-error-c3671"></a>Compilerfehler C3671

' function_1 ': die Funktion überschreibt ' function_2 ' nicht.

Wenn eine explizite Überschreibungs Syntax verwendet wird, generiert der Compiler einen Fehler, wenn eine Funktion nicht überschrieben wird.  Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md) schreibungen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3671 generiert.

```cpp
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```
