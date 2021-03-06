---
title: 'Operator &lt; Operator (Microsoft:: WRL)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: b438f823814e21e2da43f698471d782c88626628
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226879"
---
# <a name="operatorlt-operator-microsoftwrl"></a>Operator &lt; Operator (Microsoft:: WRL)

Bestimmt, ob die Adresse eines Objekts kleiner als ein anderes ist.

## <a name="syntax"></a>Syntax

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>Parameter

*ein*<br/>
Das linke Objekt.

*b*<br/>
Das rechte Objekt.

## <a name="return-value"></a>Rückgabewert

**`true`**, wenn die Adresse *eines kleiner* als die Adresse von *b*ist. andernfalls **`false`** .

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft:: WRL-Namespace](microsoft-wrl-namespace.md)
