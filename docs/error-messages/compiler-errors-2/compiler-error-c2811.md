---
title: Compilerfehler C2811
ms.date: 11/04/2016
f1_keywords:
- C2811
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
ms.openlocfilehash: 95d6385cea95f22bbb9bbb9197dace22bd1a3adf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755251"
---
# <a name="compiler-error-c2811"></a>Compilerfehler C2811

"Typ1": von "Typ2" kann nicht geerbt werden. eine Verweis Klasse kann nur von einer Verweis Klasse oder Schnittstellen Klasse erben.

Sie haben versucht, eine nicht verwaltete Klasse als Basisklasse für eine verwaltete Klasse zu verwenden.

Im folgenden Beispiel wird C2811 generiert:

```cpp
// C2811.cpp
// compile with: /clr /c
struct S{};
ref struct T {};
ref class C : public S {};   // C2811
ref class D : public T {};   // OK
```
