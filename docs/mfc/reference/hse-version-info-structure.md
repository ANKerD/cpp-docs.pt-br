---
title: Estrutura HSE_VERSION_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HSE_VERSION_INFO
dev_langs:
- C++
helpviewer_keywords:
- HSE_VERSION_INFO structure [MFC]
ms.assetid: 4837312d-68c8-4d05-9afa-1934d7d49b20
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 78b1ed79093db179e00f262b61934ff9c293ff18
ms.contentlocale: pt-br
ms.lasthandoff: 10/09/2017

---
# <a name="hseversioninfo-structure"></a>Estrutura HSE_VERSION_INFO
Essa estrutura é apontada pelo `pVer` parâmetro o `CHttpServer::GetExtensionVersion` função de membro. Ele fornece o número de versão do ISA e uma descrição textual do ISA.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
typedef struct _HSE_VERSION_INFO {  
    DWORD dwExtensionVersion;  
    CHAR lpszExtensionDesc[HSE_MAX_EXT_DLL_NAME_LEN];  
} HSE_VERSION_INFO, *LPHSE_VERSION_INFO;  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *dwExtensionVersion*  
 O número de versão do ISA.  
  
 *lpszExtensionDesc*  
 Texto de descrição do ISA. A implementação padrão fornece o texto do espaço reservado; substituir `CHttpServer::GetExtensionVersion` para fornecer sua própria descrição.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** httpext.h  
  
## <a name="see-also"></a>Consulte também  
 [Estruturas, estilos, retornos de chamada e mapas de mensagem](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

