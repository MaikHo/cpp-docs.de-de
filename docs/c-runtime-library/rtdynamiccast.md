---
title: __RTDynamicCast
ms.date: 11/04/2016
api_name:
- __RTDynamicCast
api_location:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: 238310791baebc941ad23b798adc1ea2e7fffcbb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218506"
---
# <a name="__rtdynamiccast"></a>__RTDynamicCast

Laufzeitimplementierung des [dynamic_cast](../cpp/dynamic-cast-operator.md)-Operators.

## <a name="syntax"></a>Syntax

```cpp
PVOID __RTDynamicCast (
   PVOID inptr,
   LONG VfDelta,
   PVOID SrcType,
   PVOID TargetType,
   BOOL isReference
   ) throw(...)
```

#### <a name="parameters"></a>Parameter

*inptr*<br/>
Zeiger auf ein polymorphes Objekt.

*VfDelta*<br/>
Offset des virtuellen Funktionszeiger im Objekt.

*SrcType*<br/>
Statischer Objekttyp, auf den der `inptr`-Parameter zeigt.

*TargetType*<br/>
Beabsichtigtes Ergebnis der Umwandlung.

*isReference*<br/>
**`true`**, wenn die Eingabe ein Verweis ist. , **`false`** Wenn die Eingabe ein Zeiger ist.

## <a name="return-value"></a>Rückgabewert

Zeiger auf das entsprechende unter Objekt, wenn erfolgreich; andernfalls **null**.

## <a name="exceptions"></a>Ausnahmen

`bad_cast()`, wenn die Eingabe für `dynamic_cast<>` ein Verweis ist und die Umwandlung fehlschlägt.

## <a name="remarks"></a>Bemerkungen

Konvertiert ein Objekt vom Typ `inptr` in Typ `TargetType`. Der `inptr`-Typ muss ein Zeiger sein, wenn `TargetType` ein Zeiger ist, oder ein lvalue, wenn `TargetType` ein Verweis ist. `TargetType` muss ein Zeiger oder ein Verweis auf einen zuvor definierten Klassentyp oder ein Zeiger auf „void“ sein.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|__RTDynamicCast|rtti.h|
