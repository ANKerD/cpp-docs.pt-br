---
title: "Criando o calendário mensal controle | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7ad088f67431af58a81dc06d5b0f3352a844299e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-month-calendar-control"></a>Criando o controle de calendário mensal
Como o controle de calendário mensal é criado depende se você estiver usando o controle em uma caixa de diálogo ou criá-lo em uma janela nondialog.  
  
### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>Para usar CMonthCalCtrl diretamente em uma caixa de diálogo  
  
1.  No editor de caixa de diálogo, adicione um controle de calendário mensal para o recurso de modelo de caixa de diálogo. Especifique sua ID de controle.  
  
2.  Especifique todos os estilos necessários, usando a caixa de diálogo Propriedades do controle de calendário do mês.  
  
3.  Use o [Assistente para adição de variável de membro](../ide/adding-a-member-variable-visual-cpp.md) para adicionar uma variável de membro de tipo [CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md) com a propriedade de controle. Você pode usar este membro para chamar `CMonthCalCtrl` funções de membro.  
  
4.  Use a janela Propriedades para mapear as funções de manipulador da classe de caixa de diálogo para mensagens de qualquer notificação de controle de calendário do mês, você precisa tratar (consulte [mapeando mensagens para funções](../mfc/reference/mapping-messages-to-functions.md)).  
  
5.  Em [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), defina todos os estilos adicionais para o `CMonthCalCtrl` objeto.  
  
### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>Para usar CMonthCalCtrl em uma janela de nondialog  
  
1.  Defina o controle nas classes de exibição ou janela.  
  
2.  O controle de chamada [criar](../mfc/reference/cmonthcalctrl-class.md#create) função de membro, possivelmente em [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), possivelmente como antecipado como a janela pai [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (se você tiver a função do manipulador Subclassificação do controle). Defina estilos para o controle.  
  
## <a name="see-also"></a>Consulte também  
 [Usando CMonthCalCtrl](../mfc/using-cmonthcalctrl.md)   
 [Controles](../mfc/controls-mfc.md)
