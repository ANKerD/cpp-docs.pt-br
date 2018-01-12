---
title: Classe CDBPropSet | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs: C++
helpviewer_keywords: CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2b2523e37c3015bb49d123e99f39c1ea4bdb9045
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropset-class"></a>Classe CDBPropSet
Herda o **DBPROPSET** estrutura e adiciona um construtor que inicializa os campos de chave, bem como a `AddProperty` método de acesso.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>Membros  
  
### <a name="methods"></a>Métodos  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|Adiciona uma propriedade para o conjunto de propriedades.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|Construtor.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Conjuntos de **guidPropertySet** campo o **DBPROPSET** estrutura.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operador =](../../data/oledb/cdbpropset-operator-equal.md)|Atribui o conteúdo de uma propriedade definida para outro.|  
  
## <a name="remarks"></a>Comentários  
 Uso de provedores e consumidores de OLE DB **DBPROPSET** estruturas para transmitir matrizes de `DBPROP` estruturas. Cada `DBPROP` estrutura representa uma única propriedade que pode ser definida.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atldbcli.h  
  
## <a name="see-also"></a>Consulte também  
 [Modelos de consumidor OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referência de modelos de consumidor OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Classe CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)   
 [Estrutura DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [Estrutura DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx)