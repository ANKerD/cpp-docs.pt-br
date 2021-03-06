---
title: Adicionando um manipulador de eventos (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184161b22358f77845b5f7c4b6da0bb42f3ea15f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33324909"
---
# <a name="adding-an-event-handler-visual-c"></a>Adicionando um manipulador de eventos (Visual C++)
No editor de recursos, você poderá adicionar um novo manipulador de eventos a um controle de caixa de diálogo, ou editar um manipulador de eventos existente, usando o [Assistente de Manipulador de Eventos](../ide/event-handler-wizard.md).  
  
 Adicione um evento à classe que implementa a caixa de diálogo usando a [janela Propriedades](/visualstudio/ide/reference/properties-window). Caso deseje adicionar o evento a uma classe que não seja a classe de caixa de diálogo, use o Assistente de Manipulador de Eventos.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Para adicionar um manipulador de eventos a um controle de caixa de diálogo  
  
1.  Clique duas vezes no recurso de caixa de diálogo no [Modo de Exibição de Recursos](../windows/resource-view-window.md) para abrir o recurso de caixa de diálogo que contém o controle no [editor de caixas de diálogo](../windows/dialog-editor.md).  
  
2.  Clique com o botão direito do mouse no controle para o qual deseja manipular o evento de notificação.  
  
3.  No menu de atalho, clique em **Adicionar Manipulador de Eventos** para exibir o Assistente de Manipulador de Eventos.  
  
4.  Selecione o evento na caixa **Tipo de mensagem** para adicionar à classe selecionada na caixa **Lista de classes**.  
  
5.  Aceite o nome padrão da caixa **Nome do manipulador de funções** ou forneça o nome de sua escolha.  
  
6.  Clique em **Adicionar e editar** para adicionar o manipulador de eventos ao projeto e abra o editor de texto na nova função para adicionar o código do manipulador de eventos apropriado.  
  
     Se o tipo de mensagem selecionado já tem um manipulador de eventos para a classe selecionada, a opção **Adicionar e editar** não fica disponível e a opção **Editar código** fica disponível. Clique em **Editar código** para abrir o editor de texto na função existente.  
  
 Como alternativa, você pode adicionar manipuladores de eventos por meio da [janela Propriedades](/visualstudio/ide/reference/properties-window). Confira [Adicionando manipuladores de eventos a controles de caixa de diálogo](../windows/adding-event-handlers-for-dialog-box-controls.md) para obter mais informações.  
  
## <a name="see-also"></a>Consulte também  
 [Adicionando funcionalidade com assistentes de código](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adicionando uma classe](../ide/adding-a-class-visual-cpp.md)   
 [Adicionando uma variável de membro](../ide/adding-a-member-variable-visual-cpp.md)   
 [Adicionando uma função de membro](../ide/adding-a-member-function-visual-cpp.md)   
 [Manipulador de mensagens do MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navegando pela estrutura de classe](../ide/navigating-the-class-structure-visual-cpp.md)