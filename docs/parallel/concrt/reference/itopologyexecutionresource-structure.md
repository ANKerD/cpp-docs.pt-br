---
title: Estrutura ITopologyExecutionResource | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60a0097aded73e3e0251d38daf5da71197668d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383786"
---
# <a name="itopologyexecutionresource-structure"></a>Estrutura ITopologyExecutionResource

Uma interface para um recurso de execução, conforme definido pelo Gerenciador de recursos.

## <a name="syntax"></a>Sintaxe

```
struct ITopologyExecutionResource;
```

## <a name="members"></a>Membros

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[ITopologyExecutionResource::GetId](#getid)|Retorna o identificador exclusivo do Gerenciador de recursos para este recurso de execução.|
|[ITopologyExecutionResource::GetNext](#getnext)|Retorna uma interface para o próximo recurso de execução na ordem de enumeração.|

## <a name="remarks"></a>Comentários

Essa interface é normalmente usada para percorrer a topologia do sistema, conforme observado pelo Gerenciador de recursos.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`ITopologyExecutionResource`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** concrtrm. h

**Namespace:** simultaneidade

##  <a name="getid"></a>  Método itopologyexecutionresource:: GetID

Retorna o identificador exclusivo do Gerenciador de recursos para este recurso de execução.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Valor de retorno

O Gerenciador de recursos do identificador exclusivo para este recurso de execução.

##  <a name="getnext"></a>  Método itopologyexecutionresource:: GetNext

Retorna uma interface para o próximo recurso de execução na ordem de enumeração.

```
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Valor de retorno

Uma interface para o próximo recurso de execução na ordem de enumeração. Não se houver mais nenhum nó na ordem de enumeração do nó ao qual pertence este recurso de execução, esse método retornará o valor `NULL`.

## <a name="see-also"></a>Consulte também

[Namespace de simultaneidade](concurrency-namespace.md)
