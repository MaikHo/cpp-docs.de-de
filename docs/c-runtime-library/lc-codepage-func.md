---
title: ___lc_codepage_func
ms.date: 4/2/2020
api_name:
- ___lc_codepage_func
- _o____lc_codepage_func
api_location:
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr100.dll
- msvcr90.dll
- msvcr110.dll
- msvcrt.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- lc_codepage_func
- ___lc_codepage_func
helpviewer_keywords:
- ___lc_codepage_func
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
ms.openlocfilehash: ea740bc335981ad7e1017ab4026fdc50b8fe8893
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914126"
---
# <a name="___lc_codepage_func"></a>___lc_codepage_func

Interne CRT-Funktion. Ruft die aktuelle Codepage des Threads ab.

## <a name="syntax"></a>Syntax

```cpp
UINT ___lc_codepage_func(void);
```

## <a name="return-value"></a>Rückgabewert

Die aktuelle Codepage des Threads.

## <a name="remarks"></a>Hinweise

`___lc_codepage_func` ist eine interne CRT-Funktion, die von anderen CRT-Funktionen verwendet wird, um die aktuelle Codepage aus dem lokalen Threadspeicher für CRT-Daten abzurufen. Diese Information kann auch durch Verwendung der [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)-Funktion gewonnen werden.

Eine *Codepage* ist eine Zuordnung von Einzelbyte- oder Doppelbytecodes zu einzelnen Zeichen. Zu verschiedenen Codepages gehören verschiedene spezielle Zeichen, die normalerweise für eine Sprache oder eine Gruppe von Sprachen angepasst sind. Weitere Informationen zu Codepages finden Sie unter [Codepages](../c-runtime-library/code-pages.md).

Interne CRT-Funktionen sind implementierungsspezifisch und mit jedem neuen Release Änderungen unterworfen. Ihre Verwendung in einem Code wird nicht empfohlen.

Standardmäßig ist der globale Status dieser Funktion auf die Anwendung beschränkt. Informationen hierzu finden Sie unter [globaler Status in der CRT](global-state.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|`___lc_codepage_func`|crt\src\setlocal.h|

## <a name="see-also"></a>Weitere Informationen

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)
