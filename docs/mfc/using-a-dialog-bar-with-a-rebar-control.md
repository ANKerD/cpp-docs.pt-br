---
title: Usando uma caixa de diálogo com um controle Rebar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c881e31d178d6303939c94d68e2824fb11ec2cbd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425386"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Usando uma caixa de diálogo com um controle rebar

Conforme mencionado na [controles Rebar e bandas](../mfc/rebar-controls-and-bands.md), cada faixa pode conter apenas um filho janela (ou controle). Isso pode ser uma limitação se você quiser ter mais de uma janela filho por banda. É uma solução alternativa conveniente criar um recurso da barra de diálogo com vários controles e, em seguida, adicionar uma faixa de rebar (que contém a barra da caixa de diálogo) para o controle rebar.

Normalmente, se você quisesse que a faixa de barra da caixa de diálogo apareça transparente, você definiria o WS_EX_TRANSPARENT estendido de estilo para o objeto de barra da caixa de diálogo. No entanto, como WS_EX_TRANSPARENT tem alguns problemas com pintura corretamente o plano de fundo de uma barra de diálogo, você precisará fazer um pouco de trabalho extra para alcançar o efeito desejado.

Os detalhes de procedimento a seguir as etapas necessárias para obter transparência sem usar o WS_EX_TRANSPARENT estilo estendido.

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Para implementar uma barra de diálogo transparente em uma faixa de rebar

1. Usando o [caixa de diálogo Adicionar classe](../mfc/reference/adding-an-mfc-class.md), adicione uma nova classe (por exemplo, `CMyDlgBar`) que implementa o objeto de barra da caixa de diálogo.

1. Adicione um manipulador para a mensagem WM_ERASEBKGND.

1. No manipulador de novo, modifique o código existente para corresponder ao exemplo a seguir:

     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. Adicione um manipulador para a mensagem WM_MOVE.

1. No manipulador de novo, modifique o código existente para corresponder ao exemplo a seguir:

     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

Os novos manipuladores de simular a transparência da barra de diálogo encaminhar a mensagem WM_ERASEBKGND para a janela pai e forçando um redesenho toda vez que o objeto de barra da caixa de diálogo será movido.

## <a name="see-also"></a>Consulte também

[Usando CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

