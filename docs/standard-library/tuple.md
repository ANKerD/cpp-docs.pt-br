---
title: '&lt;tuple&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <tuple>
dev_langs:
- C++
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ba25328b86a51e34cba60bd55b63ce2eab696d6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864578"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Define um modelo `tuple` cujas instâncias mantêm objetos de tipos variados.

## <a name="syntax"></a>Sintaxe

```cpp
#include <tuple>
```

### <a name="classes"></a>Classes

|Classe|Descrição|
|-|-|
|[tuple](../standard-library/tuple-class.md)|Encapsula uma sequência de comprimento fixo de elementos.|
|[Classe tuple_element](../standard-library/tuple-element-class-tuple.md)|Encapsula o tipo de um elemento `tuple`.|
|[Classe tuple_size](../standard-library/tuple-size-class-tuple.md)|Encapsula contagem de elemento `tuple`.|

### <a name="operators"></a>Operadores

|Operador|Descrição|
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Comparação de objetos `tuple`, igual a|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Comparação de objetos `tuple`, diferente de|
|[operator<](../standard-library/tuple-operators.md#op_lt)|Comparação de objetos `tuple`, menor que|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|Comparação de objetos `tuple`, menor que ou igual a|
|[operator>](../standard-library/tuple-operators.md#op_gt)|Comparação de objetos `tuple`, maior que|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|Comparação de objetos `tuple`, maior que ou igual a|

### <a name="functions"></a>Funções

|Função|Descrição|
|-|-|
|[get](../standard-library/tuple-functions.md#get)|Obtém um elemento de um objeto `tuple`.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Constitui uma `tuple` dos valores de elemento.|
|[tie](../standard-library/tuple-functions.md#tie)|Constitui um `tuple` das referências do elemento.|

## <a name="see-also"></a>Consulte também

[\<array>](../standard-library/array.md)<br/>
