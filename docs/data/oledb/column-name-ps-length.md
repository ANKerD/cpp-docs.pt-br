---
title: COLUMN_NAME_PS_LENGTH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_NAME_PS_LENGTH
dev_langs: C++
helpviewer_keywords: COLUMN_NAME_PS_LENGTH macro
ms.assetid: 415a154b-cb7c-4072-9e7d-8cfa32a15d6e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 69a8165e9179685f62c4232ac3fbec3220d22d17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="columnnamepslength"></a>COLUMN_NAME_PS_LENGTH
Representa uma associação no conjunto de linhas para a coluna específica no conjunto de linhas. Semelhante ao [COLUMN_NAME](../../data/oledb/column-name.md), exceto que essa macro também usa o comprimento de precisão, escala e coluna.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
COLUMN_NAME_PS_LENGTH(  
pszName  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length )  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pszName`  
 [in] Um ponteiro para o nome da coluna. O nome deve ser uma cadeia de caracteres Unicode. Você pode fazer isso colocando um 'L' na frente do nome, por exemplo: `L"MyColumn"`.  
  
 `nPrecision`  
 [in] A precisão máxima da coluna que você deseja vincular.  
  
 `nScale`  
 [in] A escala da coluna que você deseja vincular.  
  
 `data`  
 [in] O membro de dados correspondente no registro do usuário.  
  
 *length*  
 [in] A variável a ser associado para o comprimento da coluna.  
  
## <a name="remarks"></a>Comentários  
 Consulte [COLUMN_NAME](../../data/oledb/column-name.md) para obter informações sobre onde o **COLUMN_NAME_\***  macros são usadas.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** atldbcli.h  
  
## <a name="see-also"></a>Consulte também  
 [Macros e funções globais para modelos de consumidor OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [NOME DA COLUNA](../../data/oledb/column-name.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)