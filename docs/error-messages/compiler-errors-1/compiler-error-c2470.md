---
title: Compilerfehler C2470
ms.date: 11/04/2016
f1_keywords:
- C2470
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
ms.openlocfilehash: 0f81ba26f346508c0178a99c537206762476b7cb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743743"
---
# <a name="compiler-error-c2470"></a>Compilerfehler C2470

"Function": sieht wie eine Funktionsdefinition aus, aber es gibt keine Parameterliste. der sichtbare Text wird übersprungen.

In einer Funktionsdefinition fehlt die Argumentliste.

Im folgenden Beispiel wird C2470 generiert:

```cpp
// C2470.cpp
int MyFunc {};  // C2470
void MyFunc2() {};  //OK

int main(){
   MyFunc();
   MyFunc2();
}
```
