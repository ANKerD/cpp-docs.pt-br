---
title: Classe message_processor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3ff478b4471916fb51931ea59712be0d47d2b61
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404024"
---
# <a name="messageprocessor-class"></a>Classe message_processor

O `message_processor` classe é a classe base abstrata para o processamento de `message` objetos. Não há nenhuma garantia sobre a ordenação das mensagens.

## <a name="syntax"></a>Sintaxe

```
template<class T>
class message_processor;
```

#### <a name="parameters"></a>Parâmetros

*T*<br/>
O tipo de dados da carga mensagens manipuladas por este `message_processor` objeto.

## <a name="members"></a>Membros

### <a name="public-typedefs"></a>Typedefs públicos

|Nome|Descrição|
|----------|-----------------|
|`type`|Um alias de tipo para `T`.|

### <a name="public-methods"></a>Métodos públicos

|Nome|Descrição|
|----------|-----------------|
|[async_send](#async_send)|Quando substituído em uma classe derivada, coloca as mensagens no bloco de forma assíncrona.|
|[sync_send](#sync_send)|Quando substituído em uma classe derivada, coloca as mensagens no bloco de forma síncrona.|
|[wait](#wait)|Quando substituído em uma classe derivada, aguarda todas as operações assíncronas concluir.|

### <a name="protected-methods"></a>Métodos Protegidos

|Nome|Descrição|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Quando substituído em uma classe derivada, executa o processamento de encaminhamento de mensagens em um bloco. Chamado uma vez sempre que uma nova mensagem for adicionada e a fila é encontrada para ficar vazio.|

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`message_processor`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** Agents. h

**Namespace:** simultaneidade

##  <a name="async_send"></a> async_send

Quando substituído em uma classe derivada, coloca as mensagens no bloco de forma assíncrona.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parâmetros

*_Msg*<br/>
Um `message` objeto a ser enviado de forma assíncrona.

### <a name="remarks"></a>Comentários

Implementações do processador devem substituir este método.

##  <a name="process_incoming_message"></a> process_incoming_message

Quando substituído em uma classe derivada, executa o processamento de encaminhamento de mensagens em um bloco. Chamado uma vez sempre que uma nova mensagem for adicionada e a fila é encontrada para ficar vazio.

```
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Comentários

Implementações de bloco de mensagens devem substituir este método.

##  <a name="sync_send"></a> sync_send

Quando substituído em uma classe derivada, coloca as mensagens no bloco de forma síncrona.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parâmetros

*_Msg*<br/>
Um `message` objeto a ser enviado de forma síncrona.

### <a name="remarks"></a>Comentários

Implementações do processador devem substituir este método.

##  <a name="wait"></a> Aguarde

Quando substituído em uma classe derivada, aguarda todas as operações assíncronas concluir.

```
virtual void wait() = 0;
```

### <a name="remarks"></a>Comentários

Implementações do processador devem substituir este método.

## <a name="see-also"></a>Consulte também

[Namespace de simultaneidade](concurrency-namespace.md)<br/>
[Classe ordered_message_processor](ordered-message-processor-class.md)
