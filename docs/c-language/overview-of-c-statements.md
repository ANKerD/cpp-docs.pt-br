---
title: Visão geral de instruções de C | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a3cf80e6237b21101f737f496eb39688ec6ed0a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32387171"
---
# <a name="overview-of-c-statements"></a>Visão geral de instruções C
As instruções C consistem em tokens, expressões e outras instruções. Uma instrução que forma um componente de outra instrução chama-se o “corpo” da instrução pertinente. Cada tipo de instrução fornecido pela sintaxe a seguir será discutido nesta seção.  
  
## <a name="syntax"></a>Sintaxe  
 *statement*:  
 [labeled-statement](../c-language/goto-and-labeled-statements-c.md)  
  
 [compound-statement](../c-language/compound-statement-c.md)  
  
 [expression-statement](../c-language/expression-statement-c.md)  
  
 [selection-statement](../c-language/if-statement-c.md)  
  
 [iteration-statement](../c-language/do-while-statement-c.md)  
  
 [jump-statement](../c-language/break-statement-c.md)  
  
 [try-except-statement](../c-language/try-except-statement-c.md)  
  
 /* Específico da Microsoft \*/[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Específico da Microsoft \*/  
  
 Geralmente, o corpo da instrução é uma “instrução composta”. Uma instrução composta consiste em outras instruções que podem incluir palavras-chave. A instrução compound é delimitada por chaves (**{ }**). Todas as outras instruções C terminam com ponto-e-vírgula (**;**). O ponto-e-vírgula é um terminador de instrução.  
  
 A instrução da expressão contém a expressão C que pode conter operadores aritméticos ou lógicos introduzidos em [Expressões e atribuições](../c-language/expressions-and-assignments.md). A instrução null é uma instrução vazia.  
  
 Qualquer instrução C pode começar com um rótulo de identificação que consiste em um nome e dois-pontos. Como apenas a instrução `goto` reconhece rótulos de instrução, os rótulos de instrução são explicados com `goto`. Consulte [as instruções goto e labeled](../c-language/goto-and-labeled-statements-c.md) para obter mais informações.  
  
## <a name="see-also"></a>Consulte também  
 [Instruções](../c-language/statements-c.md)