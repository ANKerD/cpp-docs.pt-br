---
title: SDI e MDI | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1d8a1a902b5e1a7c09a0ed043f87bfa5c7819482
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="sdi-and-mdi"></a>SDI e MDI
MFC facilita a trabalhar com a interface de documento único (SDI) e aplicativos de interface de documentos múltiplos (MDI).  
  
 Aplicativos SDI permitem somente uma janela do quadro de documento aberto por vez. Aplicativos MDI permitem janelas de quadro ser aberto na mesma instância de um aplicativo de vários documentos. Um aplicativo MDI tem uma janela na qual MDI várias janelas filho, que são janelas com moldura próprios, podem ser abertas, cada uma contendo um documento separado. Em alguns aplicativos, as janelas filho podem ser de tipos diferentes, como o gráfico e de planilha. Nesse caso, a barra de menus pode alterar como janelas de filho MDI de tipos diferentes são ativadas.  
  
> [!NOTE]
>  No Windows 95 e posterior, aplicativos são geralmente SDI porque o sistema operacional adotou um modo de exibição "centrada no documento".  
  
 Para obter mais informações, consulte [documentos, exibições e estrutura de](../mfc/documents-views-and-the-framework.md).  
  
## <a name="see-also"></a>Consulte também  
 [Usando as classes para escrever aplicativos para Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)