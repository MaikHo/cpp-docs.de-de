---
title: Compilerfehler C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 828e5bbca0b796864ec8b364ee69c18a3b5eea00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206949"
---
# <a name="compiler-error-c2170"></a>Compilerfehler C2170

"Bezeichner": nicht als Funktion deklariert, kann nicht System intern sein.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Das Pragma-`intrinsic` wird für ein Element verwendet, das keine Funktion ist.

1. Das Pragma-`intrinsic` wird für eine Funktion ohne intrinsische Form verwendet.
