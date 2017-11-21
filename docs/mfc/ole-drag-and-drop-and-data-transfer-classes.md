---
title: "OLE arrastar e soltar dados Classes de transferência | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6bbb1f638de627f4202b30754f6748756418aca6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>Classes de transferência para arrastar e soltar dados OLE
Essas classes são usadas nas transferências de dados OLE. Permitem que os dados a serem transferidos entre aplicativos usando a área de transferência ou por meio de arrastar e soltar.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Controla a operação de arrastar e soltar do início ao fim. Essa classe determina quando a operação de arrastar inicia e quando ele termina. Ele também exibe comentários de cursor durante a operação de arrastar e soltar.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Usado quando um aplicativo fornece dados para uma transferência de dados. `COleDataSource`pode ser exibido como um objeto de área de transferência e orientada a objeto.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Representa o destino de uma operação de arrastar e soltar. Um `COleDropTarget` objeto corresponde a uma janela na tela. Determina se deve aceitar os dados solto nele e implementa a operação de remoção real.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Usado como o lado do destinatário para `COleDataSource`. `COleDataObject`objetos fornecem acesso aos dados armazenados por um `COleDataSource` objeto.  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral da classe](../mfc/class-library-overview.md)
