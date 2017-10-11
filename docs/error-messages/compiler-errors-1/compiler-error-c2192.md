---
title: C2192 de erro do compilador | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2192
dev_langs:
- C++
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c56dae7438c8c8dd7d17332f65b5c32aff16db39
ms.contentlocale: pt-br
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2192"></a>C2192 de erro do compilador
declaração de 'número' de parâmetro diferente  
  
 Uma função de C foi declarada uma segunda vez com uma lista de parâmetros diferentes. C não oferece suporte a funções sobrecarregadas.  
  
 O exemplo a seguir gera C2192:  
  
```  
// C2192.c  
// compile with: /Za /c  
void func( float, int );  
void func( int, float );   // C2192, different parameter list  
void func2( int, float );   // OK  
```
