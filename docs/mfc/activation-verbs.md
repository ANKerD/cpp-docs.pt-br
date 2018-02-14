---
title: "Ativação: Verbos | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c2a443f4ce65dcc7e9460bd016638aa5069e7e6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="activation-verbs"></a>Ativação: verbos
Este artigo explica o função verbos primários e secundários são reproduzidos em OLE [ativação](../mfc/activation-cpp.md).  
  
 Normalmente, duas vezes em um item inserido permite que o usuário editá-lo. No entanto, certos itens não funcionar dessa maneira. Por exemplo, clicando duas vezes em um item criado com o aplicativo do gravador de som não abre o servidor em uma janela separada. em vez disso, ela desempenha o som.  
  
 A razão para essa diferença de comportamento é que itens do gravador de som tem um diferente "verbo primário". O verbo primário é a ação executada quando o usuário clica duas vezes em um item OLE. Para a maioria dos tipos de itens OLE, o verbo primário é edição, que inicia o servidor que criou o item. Para alguns tipos de itens, como itens do gravador de som, o verbo primário é Play.  
  
 Muitos tipos de itens OLE oferecer suporte a apenas um verbo e editar é a mais comuns. No entanto, alguns tipos de itens de suportam a vários verbos. Por exemplo, itens de suportam do gravador de som editar como um verbo secundário.  
  
 Outro verbo usado com frequência é aberto. O verbo Open é idêntico ao editar, exceto o aplicativo de servidor é iniciado em uma janela separada. Esse verbo deve ser usado quando o aplicativo de contêiner ou o aplicativo de servidor não dá suporte a ativação no local.  
  
 Qualquer verbos que não seja o verbo primário devem ser invocados através de um comando do submenu quando o item é selecionado. Este submenu contém todos os verbos com suporte pelo item e geralmente for atingido, o *typename* **objeto** comando o **editar** menu. Para obter informações sobre o *typename* **objeto** de comando, consulte o artigo [Menus e recursos: adições de contêiner](../mfc/menus-and-resources-container-additions.md).  
  
 Os verbos que oferece suporte a um aplicativo de servidor são listados no banco de dados de registro do Windows. Se seu aplicativo de servidor é escrito com a biblioteca Microsoft Foundation Class, ele registrará automaticamente todos os verbos quando o servidor é iniciado. Caso contrário, você deve registrá-los durante a fase de inicialização do aplicativo de servidor. Para obter mais informações, consulte o artigo [registro](../mfc/registration.md).  
  
## <a name="see-also"></a>Consulte também  
 [Ativação](../mfc/activation-cpp.md)   
 [Contêineres](../mfc/containers.md)   
 [Servidores](../mfc/servers.md)
