---
title: Estrutura atomic_flag | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f763181424bafc4b8b3af41c135753dbe2f2577b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110312"
---
# <a name="atomicflag-structure"></a>Estrutura atomic_flag

Descreve um objeto que define e limpa atomicamente um **bool** sinalizador. Operações em sinalizadores atômicos são sempre livres de bloqueio.

## <a name="syntax"></a>Sintaxe

```cpp
struct atomic_flag;
```

## <a name="members"></a>Membros

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[clear](#clear)|Define o sinalizador armazenado como **falsos**.|
|[test_and_set](#test_and_set)|Define o sinalizador armazenado como **verdadeira** e retorna o valor de sinalizador inicial.|

## <a name="remarks"></a>Comentários

Objetos `atomic_flag` podem ser passados para as funções não membro [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) e [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit). Eles podem ser inicializados usando o valor `ATOMIC_FLAG_INIT`.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<atomic >

**Namespace:** std

## <a name="clear"></a>  atomic_flag::clear

Conjuntos do **bool** sinalizador armazenado em `*this` para **falso**, dentro de especificado [memory_order](../standard-library/atomic-enums.md#memory_order_enum) restrições.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parâmetros

*Ordem*<br/>
Uma [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>  atomic_flag::test_and_set

Conjuntos a **bool** sinalizador armazenado em `*this` para **true**, em especificado [memory_order](../standard-library/atomic-enums.md#memory_order_enum) restrições.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parâmetros

*Ordem*<br/>
Uma [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Valor de retorno

O valor inicial do sinalizador armazenado em `*this`.

## <a name="see-also"></a>Consulte também

[\<atomic>](../standard-library/atomic.md)<br/>
