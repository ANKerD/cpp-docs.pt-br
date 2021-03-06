---
title: Mapas de propriedade | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3fb9c5a5c18925bfcd448bb2349379262b27361
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080981"
---
# <a name="property-maps"></a>Mapas de propriedade

Além da sessão, o conjunto de linhas e o objeto de comando opcionais, cada provedor dá suporte a uma ou mais propriedades. Essas propriedades são definidas em mapas de propriedade contidos nos arquivos de cabeçalho criados pelo Assistente do provedor de banco de dados OLE. Cada arquivo de cabeçalho contém um mapa para as propriedades no grupo de propriedades OLE DB definidos para o objeto ou objetos definidos no arquivo. O arquivo de cabeçalho que contém o objeto de fonte de dados também contém o mapa de propriedade para o [propriedades de fonte de dados](https://msdn.microsoft.com/library/ms724188\(v=vs.140\).aspx). Session.h contém o mapa de propriedade para o [propriedades da sessão](/previous-versions/windows/desktop/ms714221\(v=vs.85\)). Os objetos de conjunto de linhas e o comando residem em um arquivo de cabeçalho único, chamado *projectname*RS.h. Essas propriedades são os membros de [propriedades do conjunto de linhas](/previous-versions/windows/desktop/ms711252\(v=vs.85\)) grupo.  
  
## <a name="see-also"></a>Consulte também  

[Arquitetura de modelo do provedor do OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)