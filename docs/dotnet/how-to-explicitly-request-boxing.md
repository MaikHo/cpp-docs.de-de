---
title: 'Gewusst wie: Explizites Anfordern von Boxing'
ms.date: 11/04/2016
helpviewer_keywords:
- boxing, explicitly requesting
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
ms.openlocfilehash: 721a57219c7216cb57f497011da1733c9e3eb7f2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545312"
---
# <a name="how-to-explicitly-request-boxing"></a>Gewusst wie: Explizites Anfordern von Boxing

Sie können das Boxing explizit anfordern, indem Sie einer Variablen vom Typ `Object`eine Variable zuweisen.

## <a name="example"></a>Beispiel

```cpp
// vcmcppv2_explicit_boxing3.cpp
// compile with: /clr
using namespace System;

void f(int i) {
   Console::WriteLine("f(int i)");
}

void f(Object ^o) {
   Console::WriteLine("f(Object^ o)");
}

int main() {
   int i = 5;
   Object ^ O = i;   // forces i to be boxed
   f(i);
   f(O);
   f( (Object^)i );  // boxes i
}
```

```Output
f(int i)
f(Object^ o)
f(Object^ o)
```

## <a name="see-also"></a>Siehe auch

[Boxing](../extensions/boxing-cpp-component-extensions.md)
