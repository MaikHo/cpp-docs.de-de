---
title: is_member_pointer-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_member_pointer
dev_langs: C++
helpviewer_keywords:
- is_member_pointer class
- is_member_pointer
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 196a1e19cee0fe722fbd5511fae658f87b2e1152
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ismemberpointer-class"></a>is_member_pointer-Klasse
Testet, ob der Typ ein Zeiger auf den Member ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct is_member_pointer;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `Ty` ein Zeiger auf eine Memberfunktion, ein Zeiger auf ein Memberobjekt oder ein `cv-qualified`-Formular von einem davon ist, andernfalls ist sie FALSE.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__is_member_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_member_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_member_pointer<trivial *> == false  
is_member_pointer<int trivial::*> == true  
is_member_pointer<int (functional::*)()> == true  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_member_function_pointer-Klasse](../standard-library/is-member-function-pointer-class.md)   
 [is_member_object_pointer-Klasse](../standard-library/is-member-object-pointer-class.md)   
 [is_pointer-Klasse](../standard-library/is-pointer-class.md)