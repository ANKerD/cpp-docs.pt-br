---
title: "As etapas em um aplicativo cliente HTTP típico | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ff67aa933e129d73747439f469140ae88be1778
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="steps-in-a-typical-http-client-application"></a>Etapas em um aplicativo cliente HTTP típico
A tabela a seguir mostra as etapas que você pode executar em um aplicativo de cliente HTTP típico:  
  
|Sua meta|Ações executadas|Efeitos|  
|---------------|----------------------|-------------|  
|Inicia uma sessão HTTP.|Criar um [CInternetSession](../mfc/reference/cinternetsession-class.md) objeto.|Inicializa WinInet e se conecta ao servidor.|  
|Conecte-se a um servidor HTTP.|Use [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection).|Retorna um [CHttpConnection](../mfc/reference/chttpconnection-class.md) objeto.|  
|Abra uma solicitação HTTP.|Use [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest).|Retorna um [CHttpFile](../mfc/reference/chttpfile-class.md) objeto.|  
|Envie uma solicitação HTTP.|Use [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) e [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|Localiza o arquivo. Se o arquivo não for encontrado, retorna falso.|  
|Ler o arquivo.|Use [CHttpFile](../mfc/reference/chttpfile-class.md).|Lê o número especificado de bytes usando um buffer que você fornecer.|  
|Trate exceções.|Use o [CInternetException](../mfc/reference/cinternetexception-class.md) classe.|Trata todos os tipos de exceção de Internet comuns.|  
|Encerre a sessão HTTP.|Descarte o [CInternetSession](../mfc/reference/cinternetsession-class.md) objeto.|Limpa automaticamente os identificadores de arquivos abertos e conexões.|  
  
## <a name="see-also"></a>Consulte também  
 [Extensões de Internet Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Pré-requisitos para Classes de cliente da Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Escrevendo um aplicativo cliente da Internet usando classes WinInet do MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)