---
title: NULL-Anweisung (C)
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
ms.openlocfilehash: 58825544121c6cb189b52469403effb93f5f5f8c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227815"
---
# <a name="null-statement-c"></a>NULL-Anweisung (C)

Eine "NULL-Anweisung" ist eine Anweisung, die nur ein Semikolon enthält. Sie kann an jeder Stelle stehen, an der eine Anweisung erwartet wird. Wenn eine NULL-Anweisung ausgeführt wird, passiert nichts. Dies ist die korrekte Methode, eine NULL-Anweisung zu codieren:

## <a name="syntax"></a>Syntax

> **;**

## <a name="remarks"></a>Hinweise

Anweisungen wie **`do`** , **`for`** , **`if`** und **`while`** erfordern als Anweisungstext eine ausführbare Anweisung. Die NULL-Anweisung erfüllt die Syntaxanforderung in Fällen, die keinen substanziellen Anweisungstext benötigen.

Wie bei jeder anderen C-Anweisung können Sie vor einer NULL-Anweisung eine Bezeichnung einfügen. Um ein Element zu bezeichnen, das keine Anweisung ist, z. B. die schließende Klammer einer Verbundanweisung, können Sie eine NULL-Anweisung bezeichnen und direkt vor dem Element einfügen, um dasselbe Ergebnis zu erzielen.

In diesem Beispiel wird die NULL-Anweisung veranschaulicht:

```C
for ( i = 0; i < 10; line[i++] = 0 )
     ;
```

Im Beispiel initialisiert der Schleifenausdruck der **`for`** -Anweisung `line[i++] = 0` die ersten zehn Elemente von `line` bis 0. Der Anweisungstext ist eine NULL-Anweisung, da keine weiteren Anweisungen erforderlich sind.

## <a name="see-also"></a>Siehe auch

[Anweisungen](../c-language/statements-c.md)
