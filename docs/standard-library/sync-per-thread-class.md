---
title: sync_per_thread-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
helpviewer_keywords:
- stdext::sync_per_thread
- stdext::sync_per_thread [C++], allocate
- stdext::sync_per_thread [C++], deallocate
- stdext::sync_per_thread [C++], equals
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
ms.openlocfilehash: 24c5463dc9fb80703361e374efb99fae9e103e7c
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562089"
---
# <a name="sync_per_thread-class"></a>sync_per_thread-Klasse

Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), der für jeden Thread ein getrenntes Cache-Objekt bereitstellt.

## <a name="syntax"></a>Syntax

```cpp
template <class Cache>
class sync_per_thread
```

### <a name="parameters"></a>Parameter

*Speichern*\
Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dabei kann es [`cache_chunklist`](../standard-library/cache-chunklist-class.md) sich um, [`cache_freelist`](../standard-library/cache-freelist-class.md) oder handeln [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

## <a name="remarks"></a>Bemerkungen

Zuweisungen, die `sync_per_thread` verwenden, können identisch sein, auch wenn die Zuweisung von in einem Thread zugewiesenen Blöcken nicht von einem anderen Thread aufgehoben werden kann. Wenn mit einer der Zuweisungen verwendet wird, sollten in einem Thread zugewiesene Speicherblöcke nicht für andere Threads sichtbar gemacht werden. In der Praxis bedeutet dies, dass nur ein einzelner Thread auf einen Container zugreifen kann, der eine der folgenden Zuweisungen verwendet.

### <a name="member-functions"></a>Memberfunktionen

|Memberfunktion|BESCHREIBUNG|
|-|-|
|[Jugend](#allocate)|Belegt einen Speicherblock.|
|[DEALLOCATE](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:**\<allocators>

**Namespace:** stdext

## <a name="sync_per_threadallocate"></a><a name="allocate"></a> Sync_per_thread:: zuordnen

Belegt einen Speicherblock.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parameter

*Countdown*\
Die Anzahl der zuzuweisenden Elemente im Array

### <a name="remarks"></a>Bemerkungen

Die Memberfunktion gibt das Ergebnis eines Aufrufs von `cache::allocate(count)` auf dem Cache-Objekt zurück, das zu dem aktuellen Thread gehört. Wenn kein Cache-Objekt für den aktuellen Thread zugewiesen wurde, wird zuerst eines zugewiesen.

## <a name="sync_per_threaddeallocate"></a><a name="deallocate"></a> Sync_per_thread::d ezuordnen

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

Die Memberfunktion ruft `deallocate` auf dem Cache-Objekt auf, das zu dem aktuellen Thread gehört. Wenn kein Cache-Objekt für den aktuellen Thread zugewiesen wurde, wird zuerst eines zugewiesen.

## <a name="sync_per_threadequals"></a><a name="equals"></a> Sync_per_thread:: ist Gleichheits

Vergleicht zwei Caches auf Gleichheit.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parameter

*Speichern*\
Das Cache-Objekt des Synchronisierungsfilters.

*Außer*\
Das Cache-Objekt, das auf Gleichheit verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**`false`** , wenn für dieses Objekt kein Cache Objekt zugeordnet wurde, oder für ein *anderes* im aktuellen Thread. Andernfalls wird das Ergebnis der Anwendung von `operator==` auf die beiden Cache-Objekte zurückgegeben.

### <a name="remarks"></a>Bemerkungen

## <a name="see-also"></a>Weitere Informationen

[\<allocators>](../standard-library/allocators-header.md)
