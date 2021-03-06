---
title: sync_shared-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
ms.openlocfilehash: 8b516762f0ae2f6d25c4d5109cbc9870f1254b89
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562076"
---
# <a name="sync_shared-class"></a>sync_shared-Klasse

Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), in dem ein Mutex verwendet wird, um den Zugriff auf ein Cache-Objekt zu steuern, das von allen Zuweisungen (allocator-Objekten) gemeinsam verwendet wird.

## <a name="syntax"></a>Syntax

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>Parameter

*Speichern*\
Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dabei kann es [`cache_chunklist`](../standard-library/cache-chunklist-class.md) sich um, [`cache_freelist`](../standard-library/cache-freelist-class.md) oder handeln [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

### <a name="member-functions"></a>Memberfunktionen

|Memberfunktion|BESCHREIBUNG|
|-|-|
|[Jugend](#allocate)|Belegt einen Speicherblock.|
|[DEALLOCATE](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:**\<allocators>

**Namespace:** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a> Sync_shared:: zuordnen

Belegt einen Speicherblock.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parameter

*Countdown*\
Die Anzahl der zuzuweisenden Elemente im Array

### <a name="return-value"></a>Rückgabewert

Zeiger auf das zugewiesene Objekt.

### <a name="remarks"></a>Bemerkungen

Die Memberfunktion sperrt den Mutex, ruft `cache.allocate(count)` auf, entsperrt den Mutex und gibt das Ergebnis des früheren Aufrufs an `cache.allocate(count)` zurück. `cache` stellt das aktuelle Cache-Objekt dar.

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a> Sync_shared::d ezuordnen

Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parameter

*PTR*\
Ein Zeiger auf das erste Objekt, dessen Zuordnung zum Speicherplatz aufgehoben werden soll.

*Countdown*\
Die Anzahl von Objekten, deren Zuweisung zum Speicherplatz aufgehoben werden soll.

### <a name="remarks"></a>Bemerkungen

Diese Memberfunktion sperrt den Mutex, ruft `cache.deallocate(ptr, count)` auf, wobei `cache` das Cache-Objekt darstellt, und entsperrt dann den Mutex.

## <a name="sync_sharedequals"></a><a name="equals"></a> Sync_shared:: ist Gleichheits

Vergleicht zwei Caches auf Gleichheit.

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>Parameter

*Speichern*\
Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll.

*Außer*\
Das Cache-Objekt, das auf Gleichheit verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**`true`** , wenn das Ergebnis von `cache.equals(Other.cache)` , wobei `cache` das Cache Objekt darstellt, ist, **`true`** andernfalls **`false`** .

### <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[\<allocators>](../standard-library/allocators-header.md)
