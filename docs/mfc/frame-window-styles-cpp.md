---
title: Estilos de janela com moldura (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f0e4bde874fc563535b661108cb68edefd8d977
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385008"
---
# <a name="frame-window-styles-c"></a>Estilos de janela com moldura (C++)

As janelas de quadro obter com o framework são adequadas para a maioria dos programas, mas você pode obter flexibilidade adicional, usando as funções avançadas [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) e a função MFC global [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` é uma função de membro de `CWnd`.

Se você aplicar a **WS_HSCROLL** e **WS_VSCROLL** estilos para a janela de quadro principal, em vez disso, são aplicados ao **MDICLIENT** janela para que os usuários podem rolar o **MDICLIENT** área.

Se a janela **FWS_ADDTOTITLE** bit de estilo é definido (o que é o padrão), o modo de exibição indica que a janela do quadro que título a ser exibido na barra de título da janela com base no nome do documento da exibição.

## <a name="what-do-you-want-to-know-more-about"></a>O que você deseja saber mais sobre

- [Gerenciando janelas filho MDI (MDICLIENT)](../mfc/managing-mdi-child-windows.md), a janela de dentro de um quadro MDI que contém as janelas filho MDI

- [Alternando os estilos de uma janela criada por MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [Estilos de janela](../mfc/reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>Consulte também

[Janelas com moldura](../mfc/frame-windows.md)

