---
title: Estilos de controle deslizante | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 747f5d55821c6911e80087ebbad65b2169e6fc49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="slider-control-styles"></a>Estilos de controle de controle deslizante
Controles deslizantes ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) pode ter uma orientação vertical ou horizontal. Eles podem ter marcas de escala em ambos os lados, ambos os lados, ou nenhum. Eles também podem ser usados para especificar um intervalo de valores consecutivos. Essas propriedades são controladas usando estilos de controle deslizante, que você especifica ao criar o controle deslizante.  
  
 O `TBS_HORZ` e `TBS_VERT` estilos determinam a orientação do controle deslizante. Se você não especificar uma orientação, o controle deslizante é orientado horizontal.  
  
 O `TBS_AUTOTICKS` estilo cria um controle deslizante que tem uma marca de escala para cada incremento em seu intervalo de valores. Essas marcas de escala são adicionadas automaticamente quando você chama o [SetRange](../mfc/reference/csliderctrl-class.md#setrange) função de membro. Se você não especificar `TBS_AUTOTICKS`, você pode usar funções de membro, como [SetTic](../mfc/reference/csliderctrl-class.md#settic) e [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), para especificar as posições das marcas de escala. Para criar um controle deslizante que não são exibidas as marcas de escala, você pode usar o `TBS_NOTICKS` estilo.  
  
 Você pode exibir as marcas de escala em um ou ambos os lados do controle deslizante. Controles deslizantes horizontal, você pode especificar o `TBS_BOTTOM` ou `TBS_TOP` estilo. Para controles do slider vertical, você pode especificar o `TBS_RIGHT` ou `TBS_LEFT` estilo. (`TBS_BOTTOM` e `TBS_RIGHT` são as configurações padrão.) Para as marcas de escala em ambos os lados do controle deslizante em qualquer orientação, especifique o `TBS_BOTH` estilo.  
  
 Um controle deslizante pode exibir um intervalo de seleção somente se você especificar o `TBS_ENABLESELRANGE` estilo quando você criá-lo. Quando um controle deslizante tem esse estilo, as marcas de escala nas posições iniciais e final de um intervalo de seleção são exibidas como triângulos (em vez de traços verticais) e o intervalo selecionado é realçado. Por exemplo, os intervalos de seleção podem ser útil em um aplicativo simple de agendamento. O usuário pode selecionar um intervalo de marcas de escala correspondente para horas em um dia para identificar um horário agendado.  
  
 Por padrão, o comprimento do controle deslizante de um controle deslizante varia de acordo com as alterações de intervalo de seleção. Se o controle deslizante tem o **TBS_FIXEDLENGTH** estilo, o tamanho do controle deslizante permanece o mesmo, mesmo se o intervalo de seleção é alterado. Um controle deslizante que tem o **TBS_NOTHUMB** estilo não inclui um controle deslizante.  
  
## <a name="see-also"></a>Consulte também  
 [Usando CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Controles](../mfc/controls-mfc.md)
