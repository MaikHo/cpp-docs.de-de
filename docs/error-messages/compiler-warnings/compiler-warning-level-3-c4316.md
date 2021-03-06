---
title: Compilerwarnung (Stufe 3) C4316
ms.date: 11/04/2016
f1_keywords:
- C4316
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
ms.openlocfilehash: 0d920cb3dc967854d1a507d06ce31fde6a670434
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198847"
---
# <a name="compiler-warning-level-3-c4316"></a>Compilerwarnung (Stufe 3) C4316

Das Objekt, das auf dem Heap zugewiesen wird, ist für diesen Typ möglicherweise nicht ausgerichtet.

Ein über-ausgerichtetes Objekt, das mithilfe von `operator new` zugeordnet wird, hat möglicherweise nicht die angegebene Ausrichtung. Überschreiben Sie den [Operator new](../../c-runtime-library/operator-new-crt.md) und den [Operator Delete](../../c-runtime-library/operator-delete-crt.md) für über ausgerichtete Typen, sodass Sie die ausgerichteten Zuordnungs Routinen verwenden – z. b. [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) und [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Im folgenden Beispiel wird C4316 generiert:

```cpp
// C4316.cpp
// Test: cl /W3 /c C4316.cpp

__declspec(align(32)) struct S {}; // C4324

int main() {
    new S; // C4316
}
```
