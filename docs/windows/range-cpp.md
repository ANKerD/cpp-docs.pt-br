---
title: intervalo (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.range
dev_langs: C++
helpviewer_keywords: range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b95b1bfd093a12bca5398c266d6a7c8236140105
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="range-c"></a>range (C++)
Especifica um intervalo de valores permitidos para argumentos ou campos cujos valores são definidos em tempo de execução.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
      [ range(  
   low,   
   high  
) ]  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *low*  
 O valor do intervalo inferior.  
  
 *high*  
 O valor de intervalo alto.  
  
## <a name="remarks"></a>Comentários  
 O **intervalo** atributo C++ tem a mesma funcionalidade que o [intervalo](http://msdn.microsoft.com/library/windows/desktop/aa367151) atributo MIDL.  
  
## <a name="example"></a>Exemplo  
  
```  
// cpp_attr_ref_range.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);  
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);  
};  
```  
  
## <a name="requirements"></a>Requisitos  
  
### <a name="attribute-context"></a>Contexto de atributo  
  
|||  
|-|-|  
|**Aplica-se a**|Método de interface, o parâmetro de interface|  
|**Repetível**|Não|  
|**Atributos necessários.**|Nenhum|  
|**Atributos inválidos**|Nenhum|  
  
 Para obter mais informações sobre os contextos de atributo, consulte [contextos de atributo](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Consulte também  
 [Atributos IDL](../windows/idl-attributes.md)   
 [Atributos de método](../windows/method-attributes.md)   
 [Atributos de parâmetro](../windows/parameter-attributes.md)   
 [Atributos de membro de dados](../windows/data-member-attributes.md)   