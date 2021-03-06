---
title: _stat Structure st_mode-Feldkonstanten
ms.date: 11/04/2016
f1_keywords:
- S_IFCHR
- S_IFDIR
- _S_IWRITE
- S_IFMT
- _S_IFDIR
- _S_IREAD
- S_IEXEC
- _S_IEXEC
- _S_IFMT
- S_IWRITE
- S_IFREG
- S_IREAD
- _S_IFCHR
- _S_IFREG
helpviewer_keywords:
- S_IFDIR constant
- stat structure
- S_IWRITE constant
- S_IEXEC constant
- _S_IFREG constant
- S_IREAD constant
- stat structure, constants
- _S_IFMT constant
- st_mode field constants
- S_IFMT constant
- _S_IEXEC constant
- _S_IWRITE constant
- _S_IFDIR constant
- S_IFREG constant
- S_IFCHR constant
- _S_IREAD constant
- _S_IFCHR constant
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
ms.openlocfilehash: ff2b6ac806b774ae3fe80f9b3cf4b3d2e82a2a9c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744687"
---
# <a name="stat-structure-stmode-field-constants"></a>_stat Structure st_mode-Feldkonstanten

## <a name="syntax"></a>Syntax

```
#include <sys/stat.h>
```

## <a name="remarks"></a>Anmerkungen

Diese Konstanten werden verwendet, um den Dateityp im **st_mode**-Feld der [_stat-Struktur](../c-runtime-library/standard-types.md) anzugeben.

Die Bitmaskenkonstanten werden im Folgenden beschrieben:

|Konstante|Bedeutung|
|--------------|-------------|
|`_S_IFMT`|Dateitypmaske|
|`_S_IFDIR`|Verzeichnis|
|`_S_IFCHR`|Sonderzeichen (gibt ein Gerät an, falls festgelegt)|
|`_S_IFREG`|Regulär|
|`_S_IREAD`|Leseberechtigung, Besitzer|
|`_S_IWRITE`|Schreibberechtigung, Besitzer|
|`_S_IEXEC`|Ausführungs-/Suchberechtigung, Besitzer|

## <a name="see-also"></a>Siehe auch

[_stat- und _wstat-Funktionen](../c-runtime-library/reference/stat-functions.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[Standardtypen](../c-runtime-library/standard-types.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
