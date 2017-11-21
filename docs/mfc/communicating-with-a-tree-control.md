---
title: "Comunicação com um controle de árvore | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 33835dcaa40b217e9248e5c03b775f968332b687
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="communicating-with-a-tree-control"></a>Comunicando-se com um controle de árvore
Usar métodos diferentes para chamar funções de membro uma [CTreeCtrl](../mfc/reference/ctreectrl-class.md) objeto dependendo de como o objeto foi criado:  
  
-   Se o controle de árvore está em uma caixa de diálogo, use uma variável de membro de tipo `CTreeCtrl` que você criar na classe de caixa de diálogo.  
  
-   Se o controle de árvore é uma janela filho, use o `CTreeCtrl` objeto (ou ponteiro) é usado para construir o objeto.  
  
-   Se você estiver usando um `CTreeView` de objeto, use a função [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) para obter uma referência para o controle de árvore. Você pode inicializar outra referência com esse valor ou atribuir o endereço da referência a um `CTreeCtrl` ponteiro.  
  
## <a name="see-also"></a>Consulte também  
 [Usando CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Controles](../mfc/controls-mfc.md)
