---
title: Namespace Microsoft::WRL::wrappers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers
dev_langs: C++
helpviewer_keywords: Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f7633bcd784fa7b9b5f7255e25e8ddc52c5b93db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="microsoftwrlwrappers-namespace"></a>Namespace Microsoft::WRL::Wrappers
Define os tipos de wrapper de inicialização de é de aquisição de recursos (RAII) que simplificam o gerenciamento de tempo de vida de objetos, cadeias de caracteres e identificadores.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
namespace Microsoft::WRL::Wrappers;  
```  
  
## <a name="members"></a>Membros  
  
### <a name="typedefs"></a>Typedefs  
  
|Nome|Descrição|  
|----------|-----------------|  
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|  
  
### <a name="classes"></a>Classes  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Classe CriticalSection](../windows/criticalsection-class.md)|Representa um objeto de seção crítica.|  
|[Classe Event (Biblioteca de Modelos C++ do Tempo de Execução do Windows)](../windows/event-class-windows-runtime-cpp-template-library.md)|Representa um evento.|  
|[Classe HandleT](../windows/handlet-class.md)|Representa um identificador para um objeto.|  
|[Classe HString](../windows/hstring-class.md)|Fornece suporte para manipulação de identificadores HSTRING.|  
|[Classe HStringReference](../windows/hstringreference-class.md)|Representa um HSTRING que é criado a partir de uma cadeia de caracteres existente.|  
|[Classe Mutex](../windows/mutex-class1.md)|Representa um objeto de sincronização que controla exclusivamente um recurso compartilhado.|  
|[Classe RoInitializeWrapper](../windows/roinitializewrapper-class.md)|Inicializa o tempo de execução do Windows.|  
|[Classe Semaphore](../windows/semaphore-class.md)|Representa um objeto de sincronização que controla um recurso compartilhado que pode dar suporte a um número limitado de usuários.|  
|[Classe SRWLock](../windows/srwlock-class.md)|Representa um bloqueio de leitor/gravador.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Consulte também  
 [Namespace Microsoft::WRL](../windows/microsoft-wrl-namespace.md)