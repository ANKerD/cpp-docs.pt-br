---
title: Adicionando uma variável de membro (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.member.variable
dev_langs:
- C++
helpviewer_keywords:
- member variables, adding
- member variables
ms.assetid: 437783bd-8eb4-4508-8b73-7380116e9d71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dade9987358c1c160dffd0221b0421b4fab92c24
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687636"
---
# <a name="adding-a-member-variable--visual-c"></a>Adicionando uma variável de membro (Visual C++)
Adicione uma variável de membro a uma classe usando o Modo de Exibição de Classe. As variáveis de membro podem se destinar à [troca e à validação de dados](../mfc/dialog-data-exchange-and-validation.md) ou podem ser genéricas. O assistente de variável de membro de dados foi projetado especificamente para encontrar as informações relevantes e usá-las para inserir elementos nos arquivos de origem nos locais apropriados. Adicione uma variável de membro por meio do [Editor de caixas de diálogo](../windows/dialog-editor.md) em [Modo de Exibição de Recursos](../windows/resource-view-window.md) ou por meio de [Modo de Exibição de Classe](/visualstudio/ide/viewing-the-structure-of-code).  
  
> [!NOTE]
>  Quando você está projetando e implementando uma caixa de diálogo, talvez seja mais eficiente usar o Editor de caixas de diálogo para adicionar os controles de caixa de diálogo e, em seguida, implementar as variáveis de membro dos controles.  
  
### <a name="to-add-a-member-variable-for-a-dialog-control-in-resource-view-using-the-add-member-variable-wizard"></a>Para adicionar uma variável de membro a um controle de caixa de diálogo em Modo de Exibição de Recursos usando o Assistente de Adição de Variável de Membro  
  
1.  Em Modo de Exibição de Recursos, expanda o nó do projeto e o nó Caixa de Diálogo para exibir a lista de caixas de diálogo do projeto.  
  
2.  Clique duas vezes na caixa de diálogo à qual deseja adicionar a variável de membro para abri-la no Editor de caixas de diálogo.  
  
3.  Na caixa de diálogo exibida no Editor de caixas de diálogo, clique com o botão direito do mouse no controle ao qual deseja adicionar a variável de membro.  
  
4.  No menu de atalho, clique em **Adicionar Variável** para exibir o [Assistente de Adição de Variável de Membro](../ide/add-member-variable-wizard.md).  
  
    > [!NOTE]
    >  Um valor padrão já é fornecido em **ID de Controle**.  
  
5.  Forneça as informações nas caixas apropriadas do assistente. Confira [Controles de caixa de diálogo e tipos de variáveis](../ide/dialog-box-controls-and-variable-types.md) para obter mais informações.  
  
6.  Clique em **Concluir** para adicionar o código de definição e de implementação ao projeto e fechar o assistente.  
  
### <a name="to-add-a-member-variable-from-class-view-using-the-add-member-variable-wizard"></a>Para adicionar uma variável de membro por meio do Modo de Exibição de Classe usando o Assistente de Adição de Variável de Membro  
  
1.  Em [Modo de Exibição de Classe](/visualstudio/ide/viewing-the-structure-of-code), expanda o nó do projeto para exibir as classes no projeto.  
  
2.  Clique com o botão direito do mouse na classe à qual deseja adicionar uma variável.  
  
3.  No menu de atalho, clique em **Adicionar** e, em seguida, em **Adicionar Variável** para exibir o Assistente de Adição de Variável de Membro.  
  
4.  Forneça as informações nas caixas apropriadas do assistente. Confira [Assistente de Adição de Variável de Membro](../ide/add-member-variable-wizard.md) para obter detalhes.  
  
5.  Clique em **Concluir** para adicionar o código de definição e de implementação ao projeto e fechar o assistente.  
  
## <a name="see-also"></a>Consulte também  
 [Adicionando funcionalidade com assistentes de código](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adicionando uma classe](../ide/adding-a-class-visual-cpp.md)   
 [Adicionando uma função de membro](../ide/adding-a-member-function-visual-cpp.md)   
 [Manipulador de mensagens do MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navegando pela estrutura de classe](../ide/navigating-the-class-structure-visual-cpp.md)