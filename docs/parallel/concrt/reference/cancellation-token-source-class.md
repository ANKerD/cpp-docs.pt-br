---
title: Classe cancellation_token_source | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03bf785ddd5885558045f0394870e114b81e0cfe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400452"
---
# <a name="cancellationtokensource-class"></a>Classe cancellation_token_source

O `cancellation_token_source` classe representa a capacidade de cancelar qualquer operação anulável.

## <a name="syntax"></a>Sintaxe

```
class cancellation_token_source;
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[cancellation_token_source](#ctor)|Sobrecarregado. Constrói um novo `cancellation_token_source`. A fonte pode ser usada para sinalizar o cancelamento de qualquer operação anulável.|
|[~ cancellation_token_source destruidor](#dtor)||

### <a name="public-methods"></a>Métodos públicos

|Nome|Descrição|
|----------|-----------------|
|[cancel](#cancel)|Cancela o token. Qualquer `task_group`, `structured_task_group`, ou `task` que usa o token será cancelado nessa chamada e gerar uma exceção no próximo ponto de interrupção.|
|[create_linked_source](#create_linked_source)|Sobrecarregado. Cria um `cancellation_token_source` que é cancelado quando o token fornecido é cancelado.|
|[get_token](#get_token)|Retorna um token de cancelamento associado a essa fonte. O token retornado pode ser pesquisado para cancelamento ou fornecer um retorno de chamada se o cancelamento ocorrer e quando.|

### <a name="public-operators"></a>Operadores públicos

|Nome|Descrição|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`cancellation_token_source`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** pplcancellation_token. h

**Namespace:** simultaneidade

##  <a name="dtor"></a> ~ cancellation_token_source

```
~cancellation_token_source();
```

##  <a name="cancel"></a> Cancelar

Cancela o token. Qualquer `task_group`, `structured_task_group`, ou `task` que usa o token será cancelado nessa chamada e gerar uma exceção no próximo ponto de interrupção.

```
void cancel() const;
```

##  <a name="ctor"></a> cancellation_token_source

Constrói um novo `cancellation_token_source`. A fonte pode ser usada para sinalizar o cancelamento de qualquer operação anulável.

```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Parâmetros

*_Src*<br/>
Para copiar ou mover o objeto.

##  <a name="create_linked_source"></a> create_linked_source

Cria um `cancellation_token_source` que é cancelado quando o token fornecido é cancelado.

```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```

### <a name="parameters"></a>Parâmetros

*_Iter*<br/>
Tipo de iterador.

*_Src*<br/>
Um token cujo cancelamento causará o cancelamento da origem do token retornado. Observe que a origem do token retornado também pode ser cancelada independentemente da origem contida neste parâmetro.

*Iniciar*<br/>
O iterador de biblioteca padrão C++ correspondente ao início do intervalo de tokens para escuta do cancelamento.

*Encerrar*<br/>
O iterador de biblioteca padrão C++ corresponde ao final do intervalo de tokens para escuta do cancelamento.

### <a name="return-value"></a>Valor de retorno

Um `cancellation_token_source` que é cancelado quando o token fornecido pelo `_Src` parâmetro será cancelado.

##  <a name="get_token"></a> get_token

Retorna um token de cancelamento associado a essa fonte. O token retornado pode ser pesquisado para cancelamento ou fornecer um retorno de chamada se o cancelamento ocorrer e quando.

```
cancellation_token get_token() const;
```

### <a name="return-value"></a>Valor de retorno

Um token de cancelamento associado a essa fonte.

##  <a name="operator_neq"></a> operador! =

```
bool operator!= (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Parâmetros

*_Src*<br/>
Operando.

### <a name="return-value"></a>Valor de retorno

##  <a name="operator_eq"></a> operador =

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Parâmetros

*_Src*<br/>
Operando.

### <a name="return-value"></a>Valor de retorno

##  <a name="operator_eq_eq"></a> operador = =

```
bool operator== (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Parâmetros

*_Src*<br/>
Operando.

### <a name="return-value"></a>Valor de retorno

## <a name="see-also"></a>Consulte também

[Namespace de simultaneidade](concurrency-namespace.md)
