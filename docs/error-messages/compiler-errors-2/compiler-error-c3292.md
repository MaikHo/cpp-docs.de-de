---
title: Compilerfehler C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: 566c92a5dc24c28b334653c6b5507b0bd9330992
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760126"
---
# <a name="compiler-error-c3292"></a>Compilerfehler C3292

Der cli-Namespace kann nicht erneut geöffnet werden.

Der cli-Namespace kann nicht in Ihrem Code deklariert werden.  Weitere Informationen finden Sie unter [Namespaces „Platform“, „default“ und „cli“](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3292 generiert:

```cpp
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```
