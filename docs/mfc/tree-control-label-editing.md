---
title: Rótulo de controle de árvore edição | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99b3490e98ba9cf9640c4903d88064a7808c6494
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376571"
---
# <a name="tree-control-label-editing"></a>Edição do rótulo de controle de árvore

O usuário pode editar diretamente os rótulos dos itens em um controle de árvore ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) que tem o **TVS_EDITLABELS** estilo. O usuário começa a editar clicando o rótulo do item que tem o foco. Um aplicativo começa a editar usando o [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) função de membro. O controle de árvore envia a notificação quando a edição começa e quando é cancelada ou concluída. Quando a edição é concluída, você é responsável por atualizar o rótulo do item, se apropriado.

Editando rótulo começa, um controle de árvore envia um [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) mensagem de notificação. Ao processar essa notificação, você pode permitir a edição de alguns rótulos e impedir a edição de outras pessoas. Retornando 0 permite a edição e retornando diferente de zero evita a ele.

Quando o rótulo edição seja cancelada ou concluída, um controle de árvore envia um [TVN_ENDLABELEDIT](/windows/desktop/Controls/tvn-endlabeledit) mensagem de notificação. O *lParam* parâmetro é o endereço de uma [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) estrutura. O **item** membro é um [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) estrutura que identifica o item e inclui o texto editado. Você é responsável por atualizar o rótulo do item, de se apropriado, talvez depois de validar a cadeia de caracteres editada. O *pszText* membro `TV_ITEM` é 0 se a edição será cancelada.

Durante a edição de rótulos, geralmente em resposta à [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) mensagem de notificação, você pode obter um ponteiro para o controle de edição usado para edição de rótulos usando o [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) membro função. Você pode chamar o controle de edição [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) a função de membro para limitar a quantidade de texto que um usuário pode inserir ou subclasse o controle de edição para interceptar e descartar os caracteres inválidos. No entanto, observe que o controle de edição é exibido apenas *após* **TVN_BEGINLABELEDIT** é enviada.

## <a name="see-also"></a>Consulte também

[Usando CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

