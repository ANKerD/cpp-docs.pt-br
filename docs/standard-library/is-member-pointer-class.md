---
title: Classe is_member_pointer | Microsoft Docs
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
ms.openlocfilehash: 49be20f858d14552cfde1ad3fc4cecf0fc738e84
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="ismemberpointer-class"></a>Classe is_member_pointer
Testa se o tipo é um ponteiro para um membro.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <class Ty>  
struct is_member_pointer;  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Ty`  
 O tipo a ser consultado.  
  
## <a name="remarks"></a>Comentários  
 Uma instância do predicado de tipo será verdadeira se o tipo `Ty` for uma função de ponteiro para membro ou um objeto de ponteiro para membro ou uma forma `cv-qualified` de um deles; caso contrário, será falsa.  
  
## <a name="example"></a>Exemplo  
  
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
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Consulte também  
 [<type_traits>](../standard-library/type-traits.md)   
 [Classe is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)   
 [Classe is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)   
 [Classe is_pointer](../standard-library/is-pointer-class.md)