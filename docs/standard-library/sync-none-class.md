---
title: Classe sync_none | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9fe7672a925105bff3b63032a709353388143c0c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953004"
---
# <a name="syncnone-class"></a>Classe sync_none

Descreve um [filtro de sincronização](../standard-library/allocators-header.md) que não fornece nenhuma sincronização.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|`Cache`|O tipo de cache associado ao filtro de sincronização. Pode ser [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) ou [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Funções de membro

|Função de membro|Descrição|
|-|-|
|[allocate](#allocate)|Aloca um bloco de memória.|
|[deallocate](#deallocate)|Libera um número especificado de objetos do armazenamento começando em uma posição especificada.|
|[equals](#equals)|Compara a igualdade de dois caches.|

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<allocators>

**Namespace:** stdext

## <a name="allocate"></a>  sync_none::allocate

Aloca um bloco de memória.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*count*|O número de elementos na matriz a serem alocados.|

### <a name="remarks"></a>Comentários

A função membro retorna `cache.allocate(count)`, em que `cache` é o objeto de cache.

## <a name="deallocate"></a>  sync_none::deallocate

Libera um número especificado de objetos do armazenamento começando em uma posição especificada.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*ptr*|Um ponteiro para o primeiro objeto a ser desalocado do armazenamento.|
|*count*|O número de objetos a serem desalocados do armazenamento.|

### <a name="remarks"></a>Comentários

A função membro chama `cache.deallocate(ptr, count)`, em que `cache` representa o objeto de cache.

## <a name="equals"></a>  sync_none::equals

Compara a igualdade de dois caches.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------------|-----------------|
|*Cache*|O objeto de cache do filtro de sincronização.|
|*Outros*|O objeto de cache a ser comparado quanto à igualdade.|

### <a name="return-value"></a>Valor de retorno

A função membro sempre retorna **verdadeira**.

### <a name="remarks"></a>Comentários

## <a name="see-also"></a>Consulte também

[\<allocators>](../standard-library/allocators-header.md)<br/>
