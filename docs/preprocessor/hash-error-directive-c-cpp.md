---
title: '#Erro de diretiva (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2da939fe52e41e122ecd4926e34fb9c4be735ae
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540730"
---
# <a name="error-directive-cc"></a>Diretiva #error (C/C++)
O **#error** diretiva emite uma mensagem de erro especificado pelo usuário em tempo de compilação e finaliza a compilação.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>Comentários  
 
A mensagem de erro que esta política emite inclui o *token de cadeia de caracteres* parâmetro. O *token de cadeia de caracteres* parâmetro não está sujeito à expansão de macro. Essa política é mais útil durante o pré-processamento para notificar o desenvolvedor de uma inconsistência do programa ou de uma violação de restrição. O exemplo a seguir demonstra o processamento do erro durante pré-processamento:  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>Consulte também  
 
[Diretivas do pré-processador](../preprocessor/preprocessor-directives.md)