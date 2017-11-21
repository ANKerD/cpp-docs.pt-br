---
title: "Adicionando itens ao controle de cabeçalho | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 792c956d73808ef50308f8e14066f74021cc84b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-items-to-the-header-control"></a>Adicionando itens ao controle de cabeçalho
Depois de criar o controle de cabeçalho ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) em sua janela pai, adicione quantas "itens de cabeçalho" conforme necessário: normalmente um por coluna.  
  
### <a name="to-add-a-header-item"></a>Para adicionar um item de cabeçalho  
  
1.  Preparar um [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) estrutura.  
  
2.  Chamar [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), passando a estrutura.  
  
3.  Repita as etapas 1 e 2 para itens adicionais.  
  
 Para obter mais informações, consulte [adicionar um Item a um controle de cabeçalho](http://msdn.microsoft.com/library/windows/desktop/bb775238) no SDK do Windows.  
  
## <a name="see-also"></a>Consulte também  
 [Usando CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Controles](../mfc/controls-mfc.md)
