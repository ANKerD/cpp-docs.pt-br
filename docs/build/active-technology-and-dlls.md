---
title: Tecnologia ativa e DLLs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efa9a5cf17a4578fc7be9cbadc51605ee32c1650
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706245"
---
# <a name="active-technology-and-dlls"></a>Tecnologia ativa e DLLs

Tecnologia ativa permite que os servidores de objeto sejam implementados completamente dentro de uma DLL. Esse tipo de servidor é chamado de um servidor em processo. MFC não suporta completamente os servidores em processo para todos os recursos de edição visual, principalmente porque a tecnologia do Active Directory não fornece uma maneira para um servidor a ser vinculada ao loop de mensagem principal do contêiner. MFC requer acesso ao loop de mensagem do aplicativo de contêiner para manipular teclas de aceleração e processamento de tempo ocioso.

Se você estiver escrevendo um servidor de automação e o servidor não tem nenhuma interface do usuário, você pode tornar seu servidor de um servidor em processo e colocá-lo completamente em uma DLL.

## <a name="what-do-you-want-to-know-more-about"></a>Que mais você deseja saber?

- [Servidores de automação](../mfc/automation-servers.md)

## <a name="see-also"></a>Consulte também

[DLLs no Visual C++](../build/dlls-in-visual-cpp.md)