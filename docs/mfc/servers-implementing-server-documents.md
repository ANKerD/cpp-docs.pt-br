---
title: 'Servidores: Implementando documentos de servidor | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c4b8618e4951ac499d504cc68b0552ea45eed03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-server-documents"></a>Servidores: implementando documentos de servidor
Este artigo explica as etapas que necessárias para implementar com êxito um documento do servidor se você não especificou a opção de servidor OLE no Assistente do aplicativo.  
  
#### <a name="to-define-a-server-document-class"></a>Para definir uma classe de documento do servidor  
  
1.  Derive sua classe de documento da `COleServerDoc` em vez de **CDocument**.  
  
2.  Criar uma classe de item de servidor derivada de `COleServerItem`.  
  
3.  Implementar o `OnGetEmbeddedItem` a função de membro da classe de documento do servidor.  
  
     `OnGetEmbeddedItem`é chamado quando o usuário de um aplicativo de contêiner cria ou edita um item inserido. Ele deverá retornar um item que representa o documento inteiro. Isso deve ser um objeto do seu `COleServerItem`-classe derivada.  
  
4.  Substituir o `Serialize` a função de membro para serializar o conteúdo do documento. Você não precisa serializar a lista de itens do servidor, a menos que sejam usados para representar os dados nativos no documento. Para obter mais informações, consulte *itens do servidor implementando* no artigo [servidores: itens de servidor](../mfc/servers-server-items.md).  
  
 Quando um documento do servidor é criado, a estrutura registra automaticamente o documento com a DLLs do sistema OLE. Isso permite que as DLLs identificar os documentos de servidor.  
  
 Para obter mais informações, consulte [COleServerItem](../mfc/reference/coleserveritem-class.md) e [COleServerDoc](../mfc/reference/coleserverdoc-class.md) no *referência da biblioteca de classe*.  
  
## <a name="see-also"></a>Consulte também  
 [Servidores](../mfc/servers.md)   
 [Servidores: Itens do servidor](../mfc/servers-server-items.md)   
 [Servidores: Implementando um servidor](../mfc/servers-implementing-a-server.md)   
 [Servidores: implementando janelas de quadro in-loco](../mfc/servers-implementing-in-place-frame-windows.md)
