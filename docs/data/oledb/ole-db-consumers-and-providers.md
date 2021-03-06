---
title: Os consumidores do OLE DB e provedores | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b37a06ec89f0e2e21c4332a480e58c605f0d161f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110712"
---
# <a name="ole-db-consumers-and-providers"></a>Consumidores e provedores de banco de dados OLE

Arquitetura do OLE DB usa o modelo de consumidores e provedores. Um consumidor faz as solicitações de dados. Um provedor responde a essas solicitações colocando dados em um formato tabular e retorná-lo para o consumidor. Qualquer chamada que o consumidor pode fazer deve ser implementada no provedor.  
  
Um consumidor definidas tecnicamente, é qualquer aplicativo ou sistema de código (não necessariamente um componente de banco de dados OLE) que acessa dados por meio de interfaces do OLE DB. As interfaces são implementadas em um provedor. Portanto, um provedor é qualquer componente de software que implementa as interfaces OLE DB para encapsular o acesso aos dados e expô-lo a outros objetos (ou seja, os consumidores).  
  
Em termos de funções, um consumidor chama métodos em interfaces de OLE DB; um provedor OLE DB implementa as interfaces de OLE DB necessárias.  
  
OLE DB evita termos de cliente e servidor, porque essas funções não sempre faz sentido, especialmente em uma situação de n camadas. Como um consumidor pode ser um componente em uma camada que serve a outro componente, para chamá-lo um cliente componente seria confuso. Além disso, um provedor, às vezes, atua mais como um driver de banco de dados que um servidor.  
  
## <a name="see-also"></a>Consulte também  

[Programação do OLE DB](../../data/oledb/ole-db-programming.md)<br/>
[Visão geral da programação do OLE DB](../../data/oledb/ole-db-programming-overview.md)