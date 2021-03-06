---
title: Adicionando objetos e controles a um projeto ATL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.controls
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5cb510bb02f71f71b35191d3ba9c4fee6b7059d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093955"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Adicionando controles e objetos para um projeto ATL

Você pode usar um dos assistentes de código de ATL para adicionar um objeto ou um controle para seus projetos baseados em MFC ou ATL. Para cada controle ou objeto COM adicionar, o assistente gera arquivos. h e. cpp, bem como um arquivo. rgs para suporte de registro baseado em script. Os seguintes assistentes de código ATL estão disponíveis no Visual Studio:

||||
|-|-|-|
|[Objeto ATL Simples](../../atl/reference/atl-simple-object-wizard.md)|[Caixa de diálogo do ATL](../../atl/reference/atl-dialog-wizard.md)|[Controle da ATL](../../atl/reference/atl-control-wizard.md)|
|[Página de propriedades ATL](../../atl/reference/atl-property-page-wizard.md)|[Componente de página de servidor ativo do ATL](../../atl/reference/atl-active-server-page-component-wizard.md)|[Consumidor do OLE DB da ATL](../../atl/reference/atl-ole-db-consumer-wizard.md)|
|[Adicionar suporte ATL ao MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[Assistente de componente de COM+ 1.0 da ATL](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[Provedor ATL OLE DB](../../atl/reference/atl-ole-db-provider-wizard.md)|

> [!NOTE]
> Antes de adicionar um objeto ATL ao seu projeto, você deve examinar os detalhes e requisitos para o objeto em seus tópicos da Ajuda relacionados.

### <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>Para adicionar um objeto ou um controle usando o Assistente de controle do ATL

1. No Gerenciador de soluções, clique com botão direito no nó do projeto e clique em **adicionar** no menu de atalho. Clique em **Adicionar classe**.

   O [Adicionar classe](../../ide/add-class-dialog-box.md) caixa de diálogo é exibida.

2. Com a pasta ATL selecionada no painel de categorias, selecione um objeto a ser inserido no painel modelos. Clique em **aberto**. O Assistente de código para o objeto selecionado é exibida.

   > [!NOTE]
   >  Se você quiser adicionar um objeto ATL para um projeto MFC, você deve adicionar suporte ATL ao projeto existente. Você pode fazer isso seguindo as instruções em [adicionando o suporte ATL ao seu projeto do MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).

   Como alternativa, se você tentar adicionar um objeto ATL ao seu projeto MFC sem anteriormente adicionar suporte ATL, Visual Studio solicita que você especifique se deseja que o suporte ATL adicionado ao seu projeto. Clique em **Sim** para adicionar suporte ATL ao projeto e abra o assistente ATL selecionado.

## <a name="see-also"></a>Consulte também

[Assistente de Projeto da ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Tipos de projeto do Visual C++](../../ide/visual-cpp-project-types.md)<br/>
[Criando projetos para área de trabalho com Assistentes de Aplicativo](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[Princípios básicos de objetos COM da ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Programando com código de tempo de execução C e da ATL](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Configurações de projeto padrão da ATL](../../atl/reference/default-atl-project-configurations.md)

