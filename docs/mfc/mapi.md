---
title: MAPI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2ca182da3a0300604415b790c0aba138c8fd7a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439101"
---
# <a name="mapi"></a>MAPI

Este artigo descreve o Microsoft MAPI Messaging Application Programming Interface () para os desenvolvedores de aplicativos de mensagem do cliente. MFC fornece suporte para um subconjunto de MAPI na classe `CDocument` , mas não encapsula toda a API. Para obter mais informações, consulte [suporte a MAPI no MFC](../mfc/mapi-support-in-mfc.md).

MAPI é um conjunto de funções que aplicativos habilitados para email e reconhecimento de email usam para criar, manipular, transferir e armazenar mensagens de email. Ele fornece as ferramentas para definir a finalidade e o conteúdo das mensagens de email de desenvolvedores de aplicativos e lhes dá flexibilidade em seu gerenciamento de mensagens de email armazenado. MAPI também fornece uma interface comum que os desenvolvedores de aplicativos podem usar para criar habilitados para email e aplicativos com reconhecimento de email independentemente do sistema de mensagens subjacente.

Clientes de mensagens fornecem uma interface humana para interação com o Microsoft Windows Messaging System (WMS). Essa interação normalmente inclui a solicitação de serviços de provedores de compatível com MAPI, como repositórios de mensagens e catálogos de endereços.

Para obter mais informações sobre MAPI, consulte os artigos na guia no Win32 MAPI (Messaging) do SDK do Windows.

## <a name="in-this-section"></a>Nesta seção

[Suporte a MAPI no MFC](../mfc/mapi-support-in-mfc.md)

## <a name="see-also"></a>Consulte também

[CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)<br/>
[COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

