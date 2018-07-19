---
title: _com_error::HelpContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e800bd3100fa0199534f3e9bdf6646aa0ffc6860
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940892"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Seção específica da Microsoft**  
  
 Chama a função `IErrorInfo::GetHelpContext`.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Valor de retorno  
 Retorna o resultado da `IErrorInfo::GetHelpContext` para o `IErrorInfo` registrado no `_com_error` objeto. Se nenhum `IErrorInfo` é registrado, ele retorna um zero.  
  
## <a name="remarks"></a>Comentários  
 Qualquer falha ao chamar o `IErrorInfo::GetHelpContext` método é ignorado.  
  
 **Fim da seção específica da Microsoft**  
  
## <a name="see-also"></a>Consulte também  
 [Classe _com_error](../cpp/com-error-class.md)