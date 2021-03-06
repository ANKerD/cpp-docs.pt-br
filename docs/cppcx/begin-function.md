---
title: Função begin | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::begin
dev_langs:
- C++
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad73daba0bce57a19c512a53747cf8ac804e929d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101749"
---
# <a name="begin-function"></a>Função begin

Retorna um iterador que aponta para o início de uma coleção que é acessada pelo parâmetro de interface especificado.

## <a name="syntax"></a>Sintaxe

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    begin(
          IVector<T>^ v         );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    begin(
          IVectorView<T>^ v
         );

template <typename T>
    ::Platform::Collections::InputIterator<T>
    begin(
          IIterable<T>^ i         );
```

#### <a name="parameters"></a>Parâmetros

*T*<br/>
Um parâmetro de tipo de modelo.

*v*<br/>
Uma coleção de vetor\<T > ou VectorView\<T > objetos que são acessados por um IVector\<T > ou IVectorView\<T > interface.

*i*<br/>
Uma coleção de objetos arbitrários do tempo de execução do Windows que são acessados por um IIterable\<T > interface.

### <a name="return-value"></a>Valor de retorno

Um iterador que aponta para o início da coleção.

### <a name="remarks"></a>Comentários

Os primeiros dois iteradores de retorno de funções do modelo e a terceira função do modelo retornam um iterador de entrada.

O objeto que é retornado por begin de VectorIterator é um iterador proxy que armazena elementos do tipo VectorProxy\<T >. Entretanto, o objeto proxy quase nunca é visível ao código do usuário. Para obter mais informações, consulte [Coleções (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Requisitos

**Cabeçalho:** collection.h

**Namespace:** Windows::Foundation::Collections

## <a name="see-also"></a>Consulte também

[Namespace Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)