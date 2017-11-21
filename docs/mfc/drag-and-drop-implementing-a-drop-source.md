---
title: 'Arrastar e soltar: Implementando uma origem para soltar | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4ebb5968497d274c714f3d24c0c090ff71de81a1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Arrastar e soltar: implementando uma origem para soltar
Este artigo explica como obter o seu aplicativo para fornecer dados para uma operação de arrastar e soltar.  
  
 A implementação básica de uma origem para soltar é relativamente simple. A primeira etapa é determinar quais eventos iniciar uma operação de arrastar. Recomendado diretrizes de interface de usuário definem o início de uma operação de arrastar como a seleção de dados e um `WM_LBUTTONDOWN` eventos que ocorrem em um ponto de dados selecionados. Os exemplos de OLE do MFC [OCLIENT](../visual-cpp-samples.md) e [HIERSVR](../visual-cpp-samples.md) siga estas diretrizes.  
  
 Se seu aplicativo é um contêiner e os dados selecionados são vinculado ou um objeto do tipo `COleClientItem`, chame seu `DoDragDrop` função de membro. Caso contrário, construir um `COleDataSource` do objeto, inicializá-lo com a seleção e chamar o objeto de fonte de dados `DoDragDrop` função de membro. Se seu aplicativo for um servidor, use `COleServerItem::DoDragDrop`. Para obter informações sobre como personalizar o comportamento padrão de arrastar e soltar, consulte o artigo [arrastar e soltar: Personalizando](../mfc/drag-and-drop-customizing.md).  
  
 Se `DoDragDrop` retorna `DROPEFFECT_MOVE`, exclua os dados de origem do documento de origem imediatamente. Nenhum outro valor de retorno de `DoDragDrop` tem qualquer efeito sobre uma origem para soltar.  
  
 Para obter mais informações, consulte:  
  
-   [Implementando um destino de soltar](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Personalizando arrastar e soltar](../mfc/drag-and-drop-customizing.md)  
  
-   [Criação e destruição de fontes de dados e objetos de dados OLE](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Manipulação de fontes de dados e objetos de dados OLE](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>Consulte também  
 [Arrastar e soltar (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)   
 [COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)   
 [CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)
