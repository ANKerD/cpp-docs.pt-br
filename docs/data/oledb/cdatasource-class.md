---
title: Classe CDataSource | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs: C++
helpviewer_keywords: CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: feb829812bd4223ca7c348f3a2825ad3b11839a5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasource-class"></a>Classe CDataSource
Corresponde a um objeto de fonte de dados OLE DB, que representa uma conexão por meio de um provedor para uma fonte de dados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CDataSource  
```  
  
## <a name="members"></a>Membros  
  
### <a name="methods"></a>Métodos  
  
|||  
|-|-|  
|[Fechar](../../data/oledb/cdatasource-close.md)|Fecha a conexão.|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|Recupera a cadeia de caracteres de inicialização da fonte de dados que está aberto no momento.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|Obtém os valores de propriedades definidas atualmente para a fonte de dados conectada.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|Obtém o valor de uma única propriedade definido atualmente para a fonte de dados conectada.|  
|[Abrir](../../data/oledb/cdatasource-open.md)|Cria uma conexão a um provedor (fonte de dados) usando um **CLSID**, **ProgID**, ou um `CEnumerator` moniker fornecida pelo chamador.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|Abre uma fonte de dados de um arquivo especificado pelo nome de arquivo fornecida pelo usuário.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|Abre a fonte de dados especificada por uma cadeia de caracteres de inicialização.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|Permite que o usuário selecione um arquivo de vínculo de dados criado anteriormente para abrir a fonte de dados correspondente.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|Abre um objeto de fonte de dados usando a caixa de diálogo de conexão de dados.|  
  
## <a name="remarks"></a>Comentários  
 Uma ou mais sessões de banco de dados podem ser criadas para uma única conexão. Essas sessões são representadas por `CSession`. Você deve chamar [cdatasource:: Open](../../data/oledb/cdatasource-open.md) para abrir a conexão antes de criar uma sessão com `CSession::Open`.  
  
 Para obter um exemplo de como usar `CDataSource`, consulte o [CatDB](../../visual-cpp-samples.md) exemplo.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atldbcli.h  
  
## <a name="see-also"></a>Consulte também  
 [Modelos de consumidor OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referência de modelos de consumidor do OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)