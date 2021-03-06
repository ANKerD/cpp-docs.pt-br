---
title: Classe value_compare | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a3be65e867c243bd6a32dd35dd3128872a1f8d1
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234106"
---
# <a name="valuecompare-class"></a>Classe value_compare

Fornece um objeto de função que pode comparar os elementos de um hash_map comparando os valores de suas chaves para determinar sua ordem relativa no hash_map.

## <a name="syntax"></a>Sintaxe

```cpp
class value_compare
    : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
        const value_type& left,
        const value_type& right) const
    {
        return (comp(left.first, right.first));
    }

protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```

## <a name="remarks"></a>Comentários

Os critérios de comparação fornecidos por value_compare entre `value_types` de elementos inteiros contidos por um hash_map são induzidos de uma comparação entre as chaves dos respectivos elementos pela construção da classe auxiliar. O operador da função membro usa o objeto `comp` do tipo `key_compare` armazenado no objeto de função fornecido por value_compare para comparar os componentes da chave de classificação de dois elementos.

Para hash_sets e hash_multisets, que são contêineres simples nos quais os valores de chave são idênticos aos valores dos elementos, value_compare é equivalente a `key_compare`; para hash_maps e hash_multimaps eles não são, uma vez que o valor dos elementos do tipo `pair` não é idêntico ao valor da chave do elemento.

## <a name="example"></a>Exemplo

Veja o exemplo de [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) para obter um exemplo de como declarar e usar value_compare.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Consulte também

[Struct binary_function](../standard-library/binary-function-struct.md)<br/>
[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Referência da biblioteca padrão C++](../standard-library/cpp-standard-library-reference.md)<br/>
