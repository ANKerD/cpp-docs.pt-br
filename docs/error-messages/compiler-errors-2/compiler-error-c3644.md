---
title: C3644 de erro do compilador | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3644
dev_langs:
- C++
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6d4520b382a955bba04802c523faf866b1bf6e4b
ms.contentlocale: pt-br
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3644"></a>C3644 de erro do compilador
'function': não é possível compilar a função para gerar código gerenciado  
  
 A presença de algumas palavras-chave em uma função fará com que a função a ser compilado para nativo.  
  
 O exemplo a seguir gera C3644:  
  
```  
// C3644.cpp  
// compile with: /clr  
// processor: x86  
  
void __clrcall Func2(int i) {  
   __asm {}   // C3644  
}  
```
