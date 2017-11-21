---
title: Classe ComPtrRef | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef
dev_langs: C++
helpviewer_keywords: ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 34368322da73e7bd0f9e01152fd24fdac52528a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrref-class"></a>Classe ComPtrRef
Oferece suporte à infraestrutura WRL e não se destina a ser usado diretamente no seu código.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `T`  
 Um [ComPtr\<T >](../windows/comptr-class.md) tipo ou um tipo derivado dele, não apenas a interface representada pelo ComPtr.  
  
## <a name="remarks"></a>Comentários  
 Representa uma referência a um objeto do tipo ComPtr\<T >.  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Construtor ComPtrRef::ComPtrRef](../windows/comptrref-comptrref-constructor.md)|Inicializa uma nova instância da classe ComPtrRef do ponteiro especificado para outro objeto ComPtrRef.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Método ComPtrRef::GetAddressOf](../windows/comptrref-getaddressof-method.md)|Recupera o endereço de um ponteiro para a interface representado pelo objeto ComPtrRef atual.|  
|[Método ComPtrRef::ReleaseAndGetAddressOf](../windows/comptrref-releaseandgetaddressof-method.md)|Exclui o objeto ComPtrRef atual e retorna um ponteiro-para-um-ponteiro para a interface que foi representada pelo objeto ComPtrRef.|  
  
### <a name="public-operators"></a>Operadores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[Operador ComPtrRef::operator InterfaceType**](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Exclui o objeto ComPtrRef atual e retorna um ponteiro-para-um-ponteiro para a interface que foi representada pelo objeto ComPtrRef.|  
|[Operador ComPtrRef::operator T*](../windows/comptrref-operator-t-star-operator.md)|Retorna o valor da [PTR _](../windows/comptrrefbase-ptr-data-member.md) membro de dados do objeto ComPtrRef atual.|  
|[Operador ComPtrRef::operator void**](../windows/comptrref-operator-void-star-star-operator.md)|Exclui o objeto ComPtrRef atual, converte o ponteiro para a interface que foi representado pelo objeto ComPtrRef como um ponteiro-para-ponteiro-para `void`e, em seguida, retorna o ponteiro de conversão.|  
|[Operador ComPtrRef::operator*](../windows/comptrref-operator-star-operator.md)|Recupera o ponteiro para a interface representado pelo objeto ComPtrRef atual.|  
|[Operador ComPtrRef::operator==](../windows/comptrref-operator-equality-operator.md)|Indica se dois objetos ComPtrRef são iguais.|  
|[Operador ComPtrRef::operator!=](../windows/comptrref-operator-inequality-operator.md)|Indica se dois objetos ComPtrRef não são iguais.|  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Consulte também  
 [Namespace Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)