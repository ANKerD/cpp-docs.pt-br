---
title: Métodos de criação de uma barra de ferramentas | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb7e73df0944a7a6c0c7b28c04e43008fcd70b39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401051"
---
# <a name="methods-of-creating-a-toolbar"></a>Métodos de criação de uma barra de ferramentas

MFC fornece classes para criar barras de ferramentas: [CToolBar](../mfc/reference/ctoolbar-class.md) e [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (que encapsula a API de controle comum do Windows). `CToolBar` fornece toda a funcionalidade do controle da barra de ferramentas comuns, e trata muitas das configurações necessárias de controle comuns e estruturas para você. No entanto, o executável resultante geralmente será maior do que é criado usando `CToolBarCtrl`.

`CToolBarCtrl` geralmente resulta em um arquivo executável menor e você pode preferir usar `CToolBarCtrl` se você não pretende integrar a barra de ferramentas na arquitetura do MFC. Se você planeja usar `CToolBarCtrl` e integrar a barra de ferramentas na arquitetura do MFC, você deve tomar cuidado adicional para se comunicar manipulações de controle de barra de ferramentas ao MFC. Essa comunicação não é difícil; No entanto, ele é trabalho adicional é desnecessário quando você usar `CToolBar`.

Visual C++ fornece duas maneiras de aproveitar o controle de barra de ferramentas comum.

- Criar a barra de ferramentas usando `CToolBar`e, em seguida, chame [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) para obter acesso ao `CToolBarCtrl` funções de membro.

- Criar a barra de ferramentas usando [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)do construtor.

Qualquer um dos métodos lhe darão acesso às funções de membro do controle de barra de ferramentas. Quando você chama `CToolBar::GetToolBarCtrl`, ele retorna uma referência a um `CToolBarCtrl` , você pode usar o conjunto de funções de membro de objeto. Ver [CToolBar](../mfc/reference/ctoolbar-class.md) para obter informações sobre como construir e criar uma barra de ferramentas usando `CToolBar`.

## <a name="see-also"></a>Consulte também

[Usando CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

