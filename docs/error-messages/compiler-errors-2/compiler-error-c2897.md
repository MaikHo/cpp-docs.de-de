---
title: Compilerfehler C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: 22e63ce92a6d526f08e68bedb35de104be339dc3
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743372"
---
# <a name="compiler-error-c2897"></a>Compilerfehler C2897

ein debugtor/Finalizer kann keine Funktions Vorlage sein.

Dekonstruktoren oder Finalizer können nicht überladen werden. Daher ist das Deklarieren eines Debuggers als Vorlage (die eine Gruppe von Debuggern definieren würde) nicht zulässig.

## <a name="examples"></a>Beispiele

Im folgenden Beispiel wird C2897 generiert.

```cpp
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

Im folgenden Beispiel wird C2897 generiert.

```cpp
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```
