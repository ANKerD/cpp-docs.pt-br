---
title: Classe scheduler_not_attached | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
dev_langs:
- C++
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 410cb7f1af100a2740309c919989896fb7964b19
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401708"
---
# <a name="schedulernotattached-class"></a>Classe scheduler_not_attached

Esta classe descreve uma exceção gerada quando é executada uma operação que exige um agendador a ser anexado ao contexto atual e um não é.

## <a name="syntax"></a>Sintaxe

```
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Sobrecarregado. Constrói um objeto `scheduler_not_attached`.|

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** concrt. h

**Namespace:** simultaneidade

##  <a name="ctor"></a> scheduler_not_attached

Constrói um objeto `scheduler_not_attached`.

```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Parâmetros

*Mensagem*<br/>
Uma mensagem descritiva do erro.

## <a name="see-also"></a>Consulte também

[Namespace de simultaneidade](concurrency-namespace.md)<br/>
[Classe Scheduler](scheduler-class.md)
