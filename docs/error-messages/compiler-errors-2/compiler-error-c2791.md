---
title: Compilerfehler C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: d589094f117135474d1a8788867d2d571bbb5f5d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739544"
---
# <a name="compiler-error-c2791"></a>Compilerfehler C2791

Ungültige Verwendung von "Super": "Class" hat keine Basisklassen.

Das Schlüsselwort " [Super](../../cpp/super.md) " wurde im Kontext einer Member-Funktion einer Klasse verwendet, die keine Basisklassen enthält.

Im folgenden Beispiel wird C2791 generiert:

```cpp
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```
