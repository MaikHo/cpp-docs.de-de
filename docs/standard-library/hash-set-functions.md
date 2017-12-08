---
title: '&lt;hash_set&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 4fcd6f0d72d31823a0d35108f087f2ad680e2f48
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; Funktionen
|||  
|-|-|  
|[swap](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|  
  
##  <a name="swap"></a> swap  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).  
  
 Tauscht die Elemente zweier hash_sets aus.  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Das hash_set, in dem die auszutauschenden Elemente bereitgestellt werden, oder das hash_set, dessen Elemente mit denen des hash_set `left` ausgetauscht werden sollen.  
  
 `left`  
 Das hash_set, dessen Elemente mit denen des hash_set `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion `swap` ist ein Algorithmus, der auf die Containerklasse „hash_set“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/hash-set-class.md#swap)( `right`) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion  
  
 **template \<class T> void swap(T&, T&),**  
  
 in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
   
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberklasse [hash_set::swap](../standard-library/hash-set-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.  
  
##  <a name="swap_hash_multiset"></a> swap (hash_multiset)  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).  
  
 Tauscht die Elemente zweier hash_multisets aus.  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Das hash_multiset, in dem die auszutauschenden Elemente bereitgestellt werden, oder das hash_multiset, dessen Elemente mit denen des hash_multiset `left` ausgetauscht werden sollen.  
  
 `left`  
 Das hash_multiset, dessen Elemente mit denen des hash_multiset `right` ausgetauscht werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion `swap` ist ein Algorithmus, der auf die Containerklasse „hash_multiset“ spezialisiert ist, um die Memberfunktion `left.`[swap](../standard-library/hash-multiset-class.md#swap)( `right`) auszuführen. Dies ist eine Instanz der partiellen Reihenfolge von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion aus. Die allgemeine Version der Vorlagenfunktion  
  
 **template \<class T> void swap(T&, T&),**  
  
 in der Algorithmusklasse funktioniert mittels Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
   
  
### <a name="example"></a>Beispiel  
  Im Codebeispiel für die Memberklasse [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) finden Sie ein Beispiel, das die Vorlagenversion `swap` verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [<hash_set>](../standard-library/hash-set.md)


