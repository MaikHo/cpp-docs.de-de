---
title: remove_volatile-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_volatile
dev_langs: C++
helpviewer_keywords:
- remove_volatile class
- remove_volatile
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 04e4f764becaf897aa963b48ab9efc8487cf464d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="removevolatile-class"></a>remove_volatile-Klasse
Wandelt einen Typ in einen permanenten Typ um.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
struct remove_volatile;  
 
template <class T>  
using remove_volatile_t = typename remove_volatile<T>::type;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der zu ändernde Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz von `remove_volatile<T>` enthält einen geänderten Typ, der `T1` ist, wenn `T` das Format `volatile T1` hat; andernfalls `T`.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_volatile_t<volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << " remove_volatile_t<volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_volatile_t<volatile int> == int  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_volatile-Klasse](../standard-library/add-volatile-class.md)