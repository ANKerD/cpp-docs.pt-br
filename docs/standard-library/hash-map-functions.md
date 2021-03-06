---
title: Funções &lt;hash_map&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: 12ceb799ccf0944b8f0e8d48975da25c39f22505
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100944"
---
# <a name="lthashmapgt-functions"></a>Funções &lt;hash_map&gt;

|||
|-|-|
|[swap](#swap)|[swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a>  swap (hash_map)

> [!NOTE]
> Esta API está obsoleta. A alternativa é a [Classe unordered_map](../standard-library/unordered-map-class.md).

Troca os elementos de dois hash_maps.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parâmetros

*right*<br/>
O hash_map cujos elementos deverão ser trocados por aqueles do mapa *esquerdo*.

*left*<br/>
O hash_map cujos elementos deverão ser trocados por aqueles do mapa *certa*.

### <a name="remarks"></a>Comentários

A função de modelo é um algoritmo especializado na classe de contêiner hash_map para executar a função membro `left.`[swap](../standard-library/basic-ios-class.md#swap)*(right*). Trata-se de uma instância da ordenação parcial de modelos de função pelo compilador. Quando as funções de modelo são sobrecarregadas de forma que a correspondência do modelo com a chamada de função não é exclusiva, o compilador seleciona a versão mais especializada do modelo de função. A versão geral da função de modelo, **template \<class T> void swap(T&, T&)**, no arquivo de cabeçalho do algoritmo funciona por atribuição e é uma operação lenta. A versão especializada em cada contêiner é muito mais rápida, uma vez que ela pode funcionar com a representação interna da classe de contêiner.

## <a name="swap"></a>  swap

> [!NOTE]
> Esta API está obsoleta. A alternativa é a [Classe unordered_multimap](../standard-library/unordered-multimap-class.md).

Troca os elementos de dois hash_multimaps.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parâmetros

*right*<br/>
O hash_multimap cujos elementos deverão ser trocados por aqueles do mapa *esquerdo*.

*left*<br/>
O hash_multimap cujos elementos deverão ser trocados por aqueles do mapa *certa*.

### <a name="remarks"></a>Comentários

A função de modelo é um algoritmo especializado na classe de contêiner hash_multimap para executar a função de membro `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`. Trata-se de uma instância da ordenação parcial de modelos de função pelo compilador. Quando as funções de modelo são sobrecarregadas de forma que a correspondência do modelo com a chamada de função não é exclusiva, o compilador seleciona a versão mais especializada do modelo de função. A versão geral da função de modelo, **template \<class T> void swap(T&, T&)**, no arquivo de cabeçalho do algoritmo funciona por atribuição e é uma operação lenta. A versão especializada em cada contêiner é muito mais rápida, uma vez que ela pode funcionar com a representação interna da classe de contêiner.

## <a name="see-also"></a>Consulte também

[<hash_map>](../standard-library/hash-map.md)<br/>
