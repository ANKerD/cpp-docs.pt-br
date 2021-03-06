---
title: DCOMCNFG | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DCOMCNFG
dev_langs:
- C++
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46a395759322651aee75541ff0b121b608b9e74d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765272"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG é um utilitário do Windows NT 4.0 que permite que você configure várias configurações específicas do DCOM no registro. A janela DCOMCNFG tem três páginas: segurança padrão, propriedades padrão e aplicativos. No Windows 2000, uma quarta página, protocolos padrão, está presente.

## <a name="default-security-page"></a>Página de segurança padrão

Você pode usar a página de segurança padrão para especificar permissões padrão para objetos do sistema. A página de segurança padrão tem três seções: acesso, inicialização e a configuração. Para alterar de padrões uma seção, clique em correspondente **Editar padrão** botão. Essas configurações de segurança padrão são armazenadas no registro em `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.

## <a name="default-protocols-page"></a>Página de protocolos padrão

Esta página lista o conjunto de protocolos de rede disponíveis para DCOM neste computador. A ordem reflete a prioridade na qual eles serão usados; o primeiro na lista tem a prioridade mais alta. Protocolos podem ser adicionados ou excluídos desta página.

## <a name="default-properties-page"></a>Página de propriedades padrão

Na página de propriedades padrão, você deve selecionar o **habilitar COM distribuído no computador** caixa de seleção se desejar que os clientes em outros computadores para acessar COM objetos em execução neste computador. Selecionar esta opção define a `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` valor `Y`.

## <a name="applications-page"></a>Página de aplicativos

Você altere as configurações para um determinado objeto com a página de aplicativos. Basta selecionar o aplicativo na lista e clique no **propriedades** botão. A janela de propriedades tem cinco páginas:

- A página geral confirma que o aplicativo que você está trabalhando.

- A página local permite que você especifique onde o aplicativo deve ser executado quando um cliente chama `CoCreateInstance` sobre o CLSID relevante. Se você selecionar o **executar o aplicativo no computador a seguir** caixa de seleção e insira um nome de computador, em seguida, um `RemoteServerName` valor é adicionado sob o AppID desse aplicativo. Limpando a **executar o aplicativo neste computador** renomeações de caixa de seleção a `LocalService` valor `_LocalService` e, assim, a desabilita.

- A página de segurança é semelhante à página de segurança padrão encontrada na janela DCOMCNFG, exceto pelo fato de que essas configurações se aplicam somente ao aplicativo atual. Novamente, as configurações são armazenadas sob o AppID para esse objeto.

- A página de identificação identifica o usuário que é usado para executar o aplicativo.

- Página pontos de extremidade lista o conjunto de pontos de extremidade disponíveis para uso por clientes do servidor selecionado DCOM e protocolos.

## <a name="see-also"></a>Consulte também

[Serviços](../atl/atl-services.md)

