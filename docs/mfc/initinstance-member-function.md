---
title: "Função de membro InitInstance | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: InitInstance
dev_langs: C++
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c33a058c126cea4dc6ce6d51fb2d4866ceb9218f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="initinstance-member-function"></a>Função de membro InitInstance
O sistema operacional Windows permite executar mais de uma cópia ou "instância" do mesmo aplicativo. `WinMain`chamadas [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) sempre que uma nova instância do aplicativo é iniciado.  
  
 O padrão `InitInstance` implementação criada pelo Assistente de aplicativo MFC executa as seguintes tarefas:  
  
-   Como sua ação central, cria os modelos de documento que por sua vez criar documentos, exibições e janelas de quadro. Para obter uma descrição desse processo, consulte [criação do modelo de documento](../mfc/document-template-creation.md).  
  
-   Carrega as opções de arquivo padrão de um arquivo. ini ou registro do Windows, incluindo os nomes dos arquivos usados mais recentemente.  
  
-   Registra um ou mais modelos de documento.  
  
-   Para um aplicativo MDI, cria uma janela do quadro principal.  
  
-   Processa a linha de comando para abrir um documento especificado na linha de comando ou abrir um documento novo e vazio.  
  
 Você pode adicionar seu próprio código de inicialização ou modificar o código escrito pelo assistente.  
  
> [!NOTE]
>  Aplicativos MFC devem ser inicializados como apartment threaded único (STA). Se você chamar [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) no seu `InitInstance` substituir, especifique `COINIT_APARTMENTTHREADED` (em vez de `COINIT_MULTITHREADED`). Para obter mais informações, consulte PRB: aplicativos MFC para de responder quando você inicializar o aplicativo como um Multi-Threaded Apartment (828643) em [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
## <a name="see-also"></a>Consulte também  
 [CWinApp: a classe do aplicativo](../mfc/cwinapp-the-application-class.md)