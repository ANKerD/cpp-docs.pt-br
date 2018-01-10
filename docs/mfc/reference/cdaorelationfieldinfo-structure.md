---
title: Estrutura CDaoRelationFieldInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoRelationFieldInfo
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8b9d27154608a19da1e575a46ec424f11eec2e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaorelationfieldinfo-structure"></a>Estrutura CDaoRelationFieldInfo
O `CDaoRelationFieldInfo` estrutura contém informações sobre um campo em uma relação definida para objetos de acesso de dados (DAO).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
struct CDaoRelationFieldInfo  
{  
    CString m_strName;           // Primary  
    CString m_strForeignName;    // Primary  
};  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `m_strName`  
 O nome do campo na tabela primária da relação.  
  
 `m_strForeignName`  
 O nome do campo da tabela externa da relação.  
  
## <a name="remarks"></a>Comentários  
 Um objeto de relação DAO Especifica os campos em uma tabela primária e os campos em uma tabela externa que definem a relação. As referências a principal na definição de estrutura acima indicam como as informações são retornadas no `m_pFieldInfos` membro de um [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) objeto obtido chamando o [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)função de membro de classe `CDaoDatabase`.  
  
 Objetos de relação e campo relação não são representados por uma classe do MFC. Em vez disso, o DAO objetos subjacentes objetos MFC classe [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) contém uma coleção de objetos de relação, chamado de coleção de relações. Cada objeto de relação, por sua vez, contém uma coleção de objetos de campo de relação. Cada objeto de campo de relação correlaciona um campo na tabela primária com um campo da tabela externa. Juntos, os objetos de campo de relação definem um grupo de campos em cada tabela, que juntas definem a relação. `CDaoDatabase`permite que você acesse objetos com um `CDaoRelationInfo` objeto chamando o `GetRelationInfo` função de membro. O `CDaoRelationInfo` objeto, em seguida, tem um membro de dados, `m_pFieldInfos`, que aponta para uma matriz de `CDaoRelationFieldInfo` objetos.  
  
 Chamar o [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) a função de membro do que contém `CDaoDatabase` objeto cujo relações de coleção está armazenado o objeto de relação que você está interessado. Acesse o `m_pFieldInfos` membro o [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) objeto. `CDaoRelationFieldInfo`também define uma `Dump` cria a função de membro na depuração. Você pode usar `Dump` para despejar o conteúdo de um `CDaoRelationFieldInfo` objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxdao.h  
  
## <a name="see-also"></a>Consulte também  
 [Estruturas, estilos, retornos de chamada e mapas de mensagem](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Estrutura CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)