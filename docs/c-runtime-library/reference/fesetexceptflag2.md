---
title: fesetexceptflag
ms.date: 04/05/2018
api_name:
- fesetexceptflag
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fesetexceptflag
- fenv/fesetexceptflag
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
ms.openlocfilehash: b16de7ea54b5f1df21b6626febe773c8cef556f5
ms.sourcegitcommit: ba4180a2d79d7e391f2f705797505d4aedbc2a5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "76972143"
---
# <a name="fesetexceptflag"></a>fesetexceptflag

Legt die angegebenen Gleitkomma-Statusflags in der aktuellen Gleitkommaumgebung fest

## <a name="syntax"></a>Syntax

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>Parameters

*pstatus*<br/>
Zeiger auf ein **fexcept_t** Objekt, das die Werte enthält, auf die die ausnahmestatusflags festgelegt werden. Das Objekt kann auf einen früheren Aufruf von [fegetexceptflag](fegetexceptflag2.md) festgelegt werden .

*ausgenommen*<br/>
Die festzulegenden Gleitkommaausnahme-Statusflags

## <a name="return-value"></a>Rückgabewert

Wenn alle angegebenen Ausnahmestatusflags erfolgreich festgelegt wurden, wird 0 zurückgegeben. Andernfalls wird ein Wert ungleich 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die Funktion " **fesetexceptflag** " legt den Status der durch " *Exception* " angegebenen Gleit Komma Ausnahme-Statusflags auf die entsprechenden Werte fest, die im **fexcept_t** Objekt festgelegt sind, auf das von *pstatus*verwiesen wird.  Es löst die Ausnahmen aber nicht aus. Der *pstatus* -Zeiger muss auf ein gültiges **fexcept_t** Objekt zeigen, oder das nachfolgende Verhalten ist nicht definiert. Die Funktion " **fesetexceptflag** " unterstützt diese Ausnahme Makro Werte in den *Ausnahmen*, die in \<fenv. h > definiert sind:

|Ausnahmemakro|Beschreibung|
|---------------------|-----------------|
|FE_DIVBYZERO|Eine Singularität oder ein Polstellenfehler aus einer früheren Gleitkommaoperation; ein Unendlichkeitswert wurde erstellt.|
|FE_INEXACT|Die Funktion wurde gezwungen, das gespeicherte Ergebnis einer früheren Gleitkommaoperation zu runden.|
|FE_INVALID|Ein Domänenfehler ist in einer früheren Gleitkommaoperation aufgetreten.|
|FE_OVERFLOW|Ein Bereichsfehler ist aufgetreten; das Ergebnis einer früheren Gleitkommaoperation war zu groß, um dargestellt zu werden.|
|FE_UNDERFLOW|Das Ergebnis einer früheren Gleitkommaoperation war zu klein, um ganz genau dargestellt zu werden; ein nicht normaler Wert wurde erstellt.|
|FE_ALL_EXCEPT|Bitweiser OR-Operator oder alle unterstützten Gleitkommaausnahmen|

Das *excepts* -Argument kann 0 (null), eines der unterstützten Gleit Komma Ausnahme-Makros oder das bitweise OR von mindestens zwei Makros sein. Der Effekt von jedem anderen Argumentwert ist nicht definiert.

Um diese Funktion zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)`-Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>-Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fesetexceptflag**|\<fenv.h>|\<cfenv>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
