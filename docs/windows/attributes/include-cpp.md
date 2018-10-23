---
title: (C++-COM-Attribut) enthalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.include
dev_langs:
- C++
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97c7ca1f808beb7e0658338dac77819455f9ed84
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791379"
---
# <a name="include-c"></a>include (C++)

Gibt einen oder mehrere Headerdateien, die in der generierten IDL-Datei eingeschlossen werden.

## <a name="syntax"></a>Syntax

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Parameter

*HEADER_FILE*<br/>
Der Name einer Datei, die Sie möchten in der generierten IDL-Datei enthalten.

## <a name="remarks"></a>Hinweise

Die **enthalten** C++-Attribut bewirkt, dass ein `#include` Anweisung unten platziert werden die `import "docobj.idl"` -Anweisung in der generierten IDL-Datei.

Die **enthalten** C++-Attribut hat die gleiche Funktionalität wie die [enthalten](/windows/desktop/Midl/include) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt ein Beispiel zur Verwendung **enthalten**. In diesem Beispiel enthält die Datei include.h nur eine `#include` Anweisung.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)  