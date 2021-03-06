---
title: sqrt, sqrtf, sqrtl
description: API-Referenz für "sqrt", "sqrtf" und "sqrtl;" , die eine Quadratwurzel einer Gleit Komma Zahl berechnen.
ms.date: 08/31/2020
api_name:
- sqrtl
- sqrtf
- sqrt
- _o_sqrt
- _o_sqrtf
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
- api-ms-win-crt-math-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- sqrt
- sqrtf
- _sqrtl
helpviewer_keywords:
- sqrtf function
- sqrt function
- sqrtl function
- _sqrtl function
- calculating square roots
- square roots, calculating
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
ms.openlocfilehash: 17526b4e4a7eca5d36c01069dbe975bb035d1f58
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556774"
---
# <a name="sqrt-sqrtf-sqrtl"></a>sqrt, sqrtf, sqrtl

Berechnet die Quadratwurzel.

## <a name="syntax"></a>Syntax

```C
double sqrt(
   double x
);
float sqrt(
   float x
);  // C++ only
long double sqrt(
   long double x
);  // C++ only
float sqrtf(
   float x
);
long double sqrtl(
   long double x
);
#define sqrt(x) // Requires C11 or higher
```

### <a name="parameters"></a>Parameter

*Stuben*\
Nicht negativer Gleitkommawert

## <a name="remarks"></a>Hinweise

Da C++ das überladen zulässt, können Sie über Ladungen von **sqrt** aufzurufen, die- **`float`** oder- **`long double`** Typen verwenden. Wenn Sie in einem C-Programm nicht das- \<tgmath.h> Makro verwenden, um diese Funktion aufzurufen, nimmt **sqrt** immer an, und gibt es zurück **`double`** .

Wenn Sie das- \<tgmath.h> `sqrt()` Makro verwenden, bestimmt der Typ des Arguments, welche Version der Funktion ausgewählt ist. Weitere Informationen finden Sie unter [Type-Generic Math](../../c-runtime-library/tgmath.md) .

Standardmäßig ist der globale Status dieser Funktion auf die Anwendung beschränkt. Informationen hierzu finden Sie unter [globaler Status in der CRT](../global-state.md).

## <a name="return-value"></a>Rückgabewert

Die **sqrt** -Funktionen geben die Quadratwurzel von *x*zurück. Wenn *x* negativ ist, gibt **sqrt** standardmäßig einen unbestimmten NaN-Wert zurück.

|Eingabe|SEH-Ausnahme|**_matherr** Distanzieren|
|-----------|-------------------|--------------------------|
|± QNAN,IND|Keine|_DOMAIN|
|- ∞|Keine|_DOMAIN|
|x<0|Keine|_DOMAIN|

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**sqrt**, **sqrtf**, **sqrtl**|\<math.h>|\<cmath>|
|**sqrt ()** -Makro | \<tgmath.h> ||

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_sqrt.c
// This program calculates a square root.

#include <math.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   double question = 45.35, answer;
   answer = sqrt( question );
   if( question < 0 )
      printf( "Error: sqrt returns %f\n", answer );
   else
      printf( "The square root of %.2f is %.2f\n", question, answer );
}
```

```Output
The square root of 45.35 is 6.73
```

## <a name="see-also"></a>Weitere Informationen

[Gleit Komma Unterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
[_CIsqrt](../../c-runtime-library/cisqrt.md)<br/>
