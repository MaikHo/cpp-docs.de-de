---
title: Support_error_info (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.support_error_info
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
ms.openlocfilehash: cf02af793b97c55de4c52280ad2795a460a98d9f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832177"
---
# <a name="support_error_info"></a>support_error_info

Implementiert die Unterstützung für die Zurückgabe ausführlicher Fehler.

## <a name="syntax"></a>Syntax

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>Parameter

*error_interface*<br/>
Der Bezeichner der Schnittstelle, die implementiert `IErrorInfo` .

## <a name="remarks"></a>Bemerkungen

Das **support_error_info** C++-Attribut implementiert die Unterstützung für die Zurückgabe ausführlicher, kontextbezogener Fehler am Zielobjekt an den Client. Damit das-Objekt Fehler unterstützt, müssen die Methoden der- `IErrorInfo` Schnittstelle durch das-Objekt implementiert werden. Weitere Informationen finden Sie unter [Unterstützung IDispatch und IErrorInfo](../../atl/supporting-idispatch-and-ierrorinfo.md).

Dieses Attribut fügt dem Zielobjekt die [ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md) -Klasse als Basisklasse hinzu. Dies führt zu einer Standard Implementierung von `ISupportErrorInfo` und kann verwendet werden, wenn eine einzelne Schnittstelle Fehler für ein Objekt generiert.

## <a name="example"></a>Beispiel

Der folgende Code fügt dem-Objekt die Standardunterstützung für die- `ISupportErrorInfo` Schnittstelle hinzu `CMyClass` .

```cpp
// cpp_attr_ref_support_error_info.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="mymod")];
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]
__interface IMyErrors
{
};

[ coclass, support_error_info("IMyErrors"),
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]
class CMyClass
{
};
```

## <a name="requirements"></a>Requirements (Anforderungen)

| Attribut Kontext | Wert |
|-|-|
|**Zielgruppe**|**`class`**|
|**REPEATABLE**|Ja|
|**Erforderliche Attribute**|Keine|
|**Ungültige Attribute**|Keine|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Weitere Informationen

[COM-Attribute](com-attributes.md)<br/>
[Klassenattribute](class-attributes.md)
