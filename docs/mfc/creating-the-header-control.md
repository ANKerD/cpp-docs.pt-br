---
title: "Criando o controle de cabeçalho | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c47e458d4cd6e9df556eef5e1f61806633208011
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-header-control"></a>Criando o controle de cabeçalho
O controle de cabeçalho não está diretamente disponível no editor de caixa de diálogo (embora você pode adicionar um controle de lista, que inclui um controle de cabeçalho).  
  
### <a name="to-put-a-header-control-in-a-dialog-box"></a>Para colocar um controle de cabeçalho em uma caixa de diálogo  
  
1.  Inserir manualmente uma variável de membro de tipo [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) em sua classe de caixa de diálogo.  
  
2.  Em [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), criar e definir os estilos para o `CHeaderCtrl`, posicioná-lo e exibi-lo.  
  
3.  Adicione itens ao controle de cabeçalho.  
  
4.  Use a janela Propriedades para mapear as funções de manipulador da classe de caixa de diálogo para qualquer notificação de controle de cabeçalho mensagens, você precisa tratar (consulte [mapeando mensagens para funções](../mfc/reference/mapping-messages-to-functions.md)).  
  
### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Para colocar um controle de cabeçalho em um modo de exibição (não um CListView)  
  
1.  Inserir uma [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) objeto em sua classe de exibição.  
  
2.  Estilo, posição e exibir a janela de controle de cabeçalho na exibição de [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) função de membro.  
  
3.  Adicione itens ao controle de cabeçalho.  
  
4.  Use a janela Propriedades para mapear as funções de manipulador da classe de exibição para qualquer notificação de controle de cabeçalho mensagens, você precisa tratar (consulte [mapeando mensagens para funções](../mfc/reference/mapping-messages-to-functions.md)).  
  
 Em ambos os casos, o objeto de controle inserido é criado quando o objeto de exibição ou a caixa de diálogo é criado. Em seguida, você deve chamar [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create) para criar a janela de controle. Para posicionar o controle, chame [CHeaderCtrl::Layout](../mfc/reference/cheaderctrl-class.md#layout) para determinar o tamanho inicial e a posição do controle e [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) para definir a posição em que você deseja. Em seguida, adicionar itens, conforme descrito em [adicionando itens ao controle de cabeçalho](../mfc/adding-items-to-the-header-control.md).  
  
 Para obter mais informações, consulte [criando um controle de cabeçalho](http://msdn.microsoft.com/library/windows/desktop/bb775238) no SDK do Windows.  
  
## <a name="see-also"></a>Consulte também  
 [Usando CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Controles](../mfc/controls-mfc.md)
