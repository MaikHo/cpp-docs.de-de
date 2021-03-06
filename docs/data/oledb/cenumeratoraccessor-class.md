---
title: CEnumeratorAccessor-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
ms.openlocfilehash: 0b4baa4671a013699e51a9ab28c002a680dfcd61
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838138"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor-Klasse

Wird von [CEnumerator](../../data/oledb/cenumerator-class.md) verwendet, um auf die Daten aus dem enumeratorrowset zuzugreifen.

## <a name="syntax"></a>Syntax

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="data-members"></a>Datenelemente

| Name | Beschreibung |
|-|-|
|[m_bIsParent](#bisparent)|Eine Variable, die angibt, ob der Enumerator ein übergeordneter Enumerator ist, wenn die Zeile ein Enumerator ist.|
|[m_nType](#ntype)|Eine Variable, die angibt, ob die Zeile eine Datenquelle oder einen Enumerator beschreibt.|
|[m_szDescription](#szdescription)|Die Beschreibung der Datenquelle oder des Enumerators.|
|[m_szName](#szname)|Der Name der Datenquelle oder des Enumerators.|
|[m_szParseName](#szparsename)|Eine Zeichenfolge, die an [iparser Display Name](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) übergeben werden soll, um einen Moniker für die Datenquelle oder den Enumerator zu erhalten.|

## <a name="remarks"></a>Bemerkungen

Dieses Rowset besteht aus den Datenquellen und Enumeratoren, die im aktuellen Enumerator sichtbar sind.

## <a name="cenumeratoraccessorm_bisparent"></a><a name="bisparent"></a> Cenzueratoraccessor:: m_bIsParent

Eine Variable, die angibt, ob der Enumerator ein übergeordneter Enumerator ist, wenn die Zeile ein Enumerator ist.

### <a name="syntax"></a>Syntax

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) in der *OLE DB Programmierer-Referenz* .

## <a name="cenumeratoraccessorm_ntype"></a><a name="ntype"></a> Cenzueratoraccessor:: m_nType

Eine Variable, die angibt, ob die Zeile eine Datenquelle oder einen Enumerator beschreibt.

### <a name="syntax"></a>Syntax

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) in der *OLE DB Programmierer-Referenz* .

## <a name="cenumeratoraccessorm_szdescription"></a><a name="szdescription"></a> Cenzueratoraccessor:: m_szDescription

Die Beschreibung der Datenquelle oder des Enumerators.

### <a name="syntax"></a>Syntax

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) in der *OLE DB Programmierer-Referenz* .

## <a name="cenumeratoraccessorm_szname"></a><a name="szname"></a> Cenzueratoraccessor:: m_szName

Der Name der Datenquelle oder des Enumerators.

### <a name="syntax"></a>Syntax

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) in der *OLE DB Programmierer-Referenz* .

## <a name="cenumeratoraccessorm_szparsename"></a><a name="szparsename"></a> Cenzueratoraccessor:: m_szParseName

Eine Zeichenfolge, die an [iparser Display Name](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) übergeben werden soll, um einen Moniker für die Datenquelle oder den Enumerator zu erhalten.

### <a name="syntax"></a>Syntax

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) in der *OLE DB Programmierer-Referenz* .

## <a name="see-also"></a>Weitere Informationen

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz zu OLE DB Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)
