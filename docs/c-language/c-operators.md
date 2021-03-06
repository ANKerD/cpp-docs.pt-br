---
title: Operadores C | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f90f25d52a2555eb92938dd29ebb7e5bfc6e96a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="c-operators"></a>Operadores C
Os operadores C são um subconjunto de [operadores embutidos de C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md).  
  
 Há três tipos de operadores. Uma expressão unária consiste em um operador unário pré-anexado a um operando ou na palavra-chave `sizeof` seguida de uma expressão. A expressão pode ser o nome de uma variável ou uma expressão de conversão. Se a expressão for uma expressão de conversão, ela deverá ser colocada entre parênteses. Uma expressão binária consiste em dois operandos unidos por um operador binário. Uma expressão ternária consiste em três operandos unidos pelo operador de expressão condicional.  
  
 O C inclui os seguintes operadores unários:  
  
|Símbolo|Nome|  
|------------|----------|  
|**- ~ !**|Operadores de negação e de complemento|  
|**\* &**|Operadores de indireção e address-of|  
|`sizeof`|Operador de tamanho|  
|**+**|Operador unário de adição|  
|**++ --**|Operadores unários de incremento e de decremento|  
  
 Operadores binários associados da esquerda para a direita. O C fornece os seguintes operadores binários:  
  
|Símbolo|Nome|  
|------------|----------|  
|**\* / %**|Operadores de multiplicação|  
|**+ -**|Operadores aditivos|  
|**<\< >>**|Operadores shift|  
|**\<   >   \<=   >=   ==   !=**|Operadores relacionais|  
|**&   &#124; ^**|Operadores bit a bit|  
|**&&   &#124;&#124;**|Operadores lógicos|  
|**,**|Operador de avaliação sequencial|  
  
 O operador de base (**:>**), com suporte em versões anteriores do compilador de 16 bits do Microsoft C, é descrito em [Resumo da sintaxe da linguagem C](../c-language/c-language-syntax-summary.md).  
  
 O operador de expressão condicional tem uma precedência mais baixa do que as expressões binárias e difere delas por ser associado à direita.  
  
 As expressões com operadores também incluem as expressões de atribuição, que usam operadores de atribuição unários ou binários. Os operadores de atribuição unários são operadores de incremento (`++`) e de decremento (**--**); os operadores de atribuição binários são o operador de atribuição simples (**=**) e os operadores de atribuição compostos. Cada operador de atribuição composta é uma combinação de outro operador binário com o operador de atribuição simples.  
  
## <a name="see-also"></a>Consulte também  
 [Expressões e atribuições](../c-language/expressions-and-assignments.md)