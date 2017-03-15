---
title: C3414 de erro do compilador | Documentos do Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3414
dev_langs:
- C++
helpviewer_keywords:
- C3414
ms.assetid: 715f5432-b509-4f8f-84f5-e1463bac490f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 0aee8d8860183f73f638e1ec41c6841ad45573d7
ms.lasthandoff: 02/25/2017

---
# <a name="compiler-error-c3414"></a>C3414 de erro do compilador
'member': função de membro importado não pode ser definida  
  
 Um membro foi definido no código que também esteja definido em um assembly referenciado.  
  
 O exemplo a seguir gera C3414:  
  
```  
// C3414a2.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 e, em seguida:  
  
```  
// C3414b2.cpp  
// compile with: /clr  
#using <C3414a2.dll>  
  
void MyClass::Test() {    // C3414  
}  
  
System::Object::Object() {    // C3414  
}  
```  

