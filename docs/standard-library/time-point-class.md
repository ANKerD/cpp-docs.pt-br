---
title: Classe time_point | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
dev_langs:
- C++
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::chrono [C++], time_point
ms.workload:
- cplusplus
ms.openlocfilehash: eb5390ad8fec7e355181c9711de1bb14d3b17820
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705972"
---
# <a name="timepoint-class"></a>Classe time_point

Um `time_point` descreve um tipo que representa um ponto no tempo. Ele contém um objeto do tipo [duration](../standard-library/duration-class.md) que armazena o tempo decorrido desde a época que é representada pelo argumento de modelo `Clock`.

## <a name="syntax"></a>Sintaxe

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Membros

### <a name="public-typedefs"></a>Typedefs públicos

|Nome|Descrição|
|----------|-----------------|
|`time_point::clock`|Sinônimo do parâmetro de modelo `Clock`.|
|`time_point::duration`|Sinônimo do parâmetro de modelo `Duration`.|
|`time_point::period`|Sinônimo do nome do tipo aninhado `duration::period`.|
|`time_point::rep`|Sinônimo do nome do tipo aninhado `duration::rep`.|

### <a name="public-constructors"></a>Construtores públicos

|Nome|Descrição|
|----------|-----------------|
|[time_point](#time_point)|Constrói um objeto `time_point`.|

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[max](#max)|Especifica o limite superior de `time_point::ref`.|
|[min](#min)|Especifica o limite inferior de `time_point::ref`.|
|[time_since_epoch](#time_since_epoch)|Retorna o valor `duration` armazenado.|

### <a name="public-operators"></a>Operadores públicos

|Nome|Descrição|
|----------|-----------------|
|[time_point::operator+=](#op_add_eq)|Adiciona um valor especificado à duração armazenada.|
|[time_point::operator-=](#operator-_eq)|Subtrai um valor especificado da duração armazenada.|

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<chrono >

**Namespace:** std::chrono

## <a name="max"></a>  time_point::max

Método estático que retorna o limite superior para valores do tipo `time_point::ref`.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Valor de retorno

Na verdade, retorna `time_point(duration::max())`.

## <a name="min"></a>  time_point::min

Método estático que retorna o limite inferior para valores do tipo `time_point::ref`.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Valor de retorno

Na verdade, retorna `time_point(duration::min())`.

## <a name="op_add_eq"></a>  time_point::operator+=

Adiciona um valor especificado ao valor [duration](../standard-library/duration-class.md) armazenado.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parâmetros

*Dur*<br/>
Um objeto `duration`.

### <a name="return-value"></a>Valor de retorno

O objeto `time_point` depois que a adição é executada.

## <a name="time_point__operator-_eq"></a>  time_point::operator-=

Subtrai um valor especificado do valor [duration](../standard-library/duration-class.md) armazenado.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parâmetros

*Dur*<br/>
Um objeto `duration`.

### <a name="return-value"></a>Valor de retorno

O objeto `time_point` depois que a subtração é executada.

## <a name="time_point"></a>  Construtor time_point::time_point

Constrói um objeto `time_point`.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Parâmetros

*Dur*<br/>
Um objeto [duration](../standard-library/duration-class.md).

*TP*<br/>
Um objeto `time_point`.

### <a name="remarks"></a>Comentários

O primeiro construtor constrói um objeto cujo valor `duration` armazenado é igual a [duration::zero](../standard-library/duration-class.md#zero).

O segundo construtor constrói um objeto cujo valor de duração armazenado é igual a *Dur*. A menos que `is_convertible<Duration2, duration>` será verdadeiro, o segundo construtor não participará na resolução de sobrecarga. Para obter mais informações, consulte [<type_traits>](../standard-library/type-traits.md).

O terceiro construtor inicializa seu valor `duration` usando `Tp.time_since_epoch()`.

## <a name="time_since_epoch"></a>  time_point::time_since_epoch

Recupera o valor [duration](../standard-library/duration-class.md) armazenado.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>Consulte também

[Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
