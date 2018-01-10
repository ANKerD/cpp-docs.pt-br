---
title: "– Implementação comentário | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 437b091b2237c7219a0afeee46d78164751e6d3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="-implementation-comment"></a>// Comentário da implementação
O `// Implementation` seção é a parte mais importante de qualquer declaração de classe do MFC.  
  
 Esta seção contém todos os detalhes de implementação. Variáveis de membro e funções de membro podem aparecer nesta seção. Todos os itens abaixo desta linha podem ser alteradas em uma versão futura do MFC. A menos que você não pode evitar isso, você não deve confiar em detalhes abaixo o `// Implementation` linha. Além disso, membros declarados abaixo da linha de implementação não são documentados, embora alguns implementação é discutida nas observações técnicas. Substituições de funções virtuais na classe base residem nesta seção, independentemente de qual seção a função da classe base é definida, como o fato de que uma função substitui a implementação da classe base é considerado um detalhe de implementação. Normalmente, esses membros são protegidos, mas não sempre.  
  
 Observe a partir de `CStdioFile` listando em [um exemplo dos comentários](../mfc/an-example-of-the-comments.md) que membros declarados abaixo o `// Implementation` comentário pode ser declarado como **pública**, `protected`, ou `private`. Você deve usar apenas esses membros com cuidado, pois eles podem ser alteradas no futuro. Declarando um grupo de membros como **pública** podem ser necessários para a implementação da biblioteca de classe funcione corretamente. No entanto, isso não significa que você pode usar com segurança os membros declarados assim.  
  
> [!NOTE]
>  Você pode achar os comentários dos tipos restantes acima ou abaixo de `// Implementation` comentário. Em ambos os casos, eles descrevem os tipos de membros declarados abaixo deles. Se ocorrerem abaixo o `// Implementation` comentário, você deve assumir que os membros podem mudar em versões futuras do MFC.  
  
## <a name="see-also"></a>Consulte também  
 [Usando os arquivos de origem MFC](../mfc/using-the-mfc-source-files.md)   
 [Um exemplo dos comentários](../mfc/an-example-of-the-comments.md)   
 [Construtores de comentário](../mfc/decrement-constructors-comment.md)   
 [Comentário sobre atributos](../mfc/decrement-attributes-comment.md)   
 [Comentário sobre operações](../mfc/decrement-operations-comment.md)   
 [Comentário sobre substituíveis](../mfc/decrement-overridables-comment.md)
