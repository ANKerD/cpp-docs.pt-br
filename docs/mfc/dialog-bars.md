---
title: "Barras da caixa de diálogo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d9d7319f23741f683e31cfd683a8ebd6d25acdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-bars"></a>Barras da caixa de diálogo
Uma barra da caixa de diálogo é uma barra de ferramentas, um tipo de [barra de controle](../mfc/control-bars.md) que pode conter qualquer tipo de controle. Porque ela tem as características de uma caixa de diálogo sem janela restrita, uma [CDialogBar](../mfc/reference/cdialogbar-class.md) objeto fornece uma barra de ferramentas mais avançada.  
  
 Há várias diferenças importantes entre uma barra de ferramentas e um `CDialogBar` objeto. Um `CDialogBar` objeto é criado a partir de um recurso de modelo de caixa de diálogo, que podem ser criadas com o editor de caixa de diálogo Visual C++ e que pode conter qualquer tipo de controle do Windows. O usuário pode guia de controle para controle. E você pode especificar um estilo de alinhamento para alinhar a barra da caixa de diálogo com qualquer parte da janela do quadro do pai ou deixá-lo no lugar, se o pai for redimensionado. A figura a seguir mostra uma barra da caixa de diálogo com uma variedade de controles.  
  
 ![Barra de caixa de diálogo do VC](../mfc/media/vc378t1.gif "vc378t1")  
Uma barra da caixa de diálogo  
  
 Em outros aspectos, trabalhando com um `CDialogBar` objeto é semelhante a trabalhar com uma caixa de diálogo sem janela restrita. Use o editor de caixa de diálogo para criar o recurso de caixa de diálogo.  
  
 Uma das vantagens de barras da caixa de diálogo é que eles podem incluir controles que não sejam botões.  
  
 Embora seja normal para derivar suas próprias classes de caixa de diálogo de `CDialog`, você normalmente não derivar sua própria classe para uma barra da caixa de diálogo. Barras da caixa de diálogo são extensões para uma janela principal e as mensagens de notificação de controle de barra da caixa de diálogo, como **BN_CLICKED** ou **EN_CHANGE**, serão enviados para o pai da caixa de diálogo, barras, a janela principal.  
  
## <a name="see-also"></a>Consulte também  
 [Elementos da Interface do usuário](../mfc/user-interface-elements-mfc.md)   
 [Amostra](../visual-cpp-samples.md)
