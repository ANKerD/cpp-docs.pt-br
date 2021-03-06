---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef090aec97308a6d423c18daab5ee540efdd8a1
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316309"
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;

> [!NOTE]
> Este cabeçalho é obsoleto. A alternativa é [ \<unordered_map >](unordered-map.md).

Define as classes de modelo do contêiner hash_map e hash_multimap e seus modelos de suporte.

## <a name="syntax"></a>Sintaxe

> #<a name="include-hashmap"></a>incluir \<hash_map >

### <a name="operators"></a>Operadores

|Versão hash_map|Versão hash_multimap|Descrição|
|-----------------------|----------------------------|-----------------|
|[operator!= (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Testa se o objeto hash_map ou hash_multimap no lado esquerdo do operador não é igual ao objeto hash_map ou hash_multimap no lado direito.|
|[operator== (hash_map)](hash-map-operators.md#op_eq_eq)|[operator== (hash_multimap)](hash-map-operators.md#op_eq_eq_mm)|Testa se o objeto hash_map ou hash_multimap no lado esquerdo do operador é igual ao objeto hash_map ou hash_multimap no lado direito.|

### <a name="specialized-template-functions"></a>Funções de Modelo Especializadas

|Versão hash_map|Versão hash_multimap|Descrição|
|-----------------------|----------------------------|-----------------|
|[swap (hash_map)](hash-map-class.md#swap)|[swap (hash_multimap)](hash-multimap-class.md#swap)|Troca os elementos de dois hash_maps ou hash_multimaps.|

### <a name="classes"></a>Classes

|Classe|Descrição|
|-|-|
|[Classe hash_compare](hash-compare-class.md)|Descreve um objeto que pode ser usado por qualquer um dos contêineres associativos de hash — hash_map, hash_multimap, hash_set ou hash_multiset — como um padrão `Traits` objeto de parâmetro para ordenar e fazer o hash dos elementos que eles contêm.|
|[Classe value_compare](value-compare-class.md)|Fornece um objeto de função que pode comparar os elementos de um hash_map comparando os valores de suas chaves para determinar sua ordem relativa no hash_map.|
|[Classe hash_map](hash-map-class.md)|Usado para o armazenamento e a recuperação rápida de dados de uma coleção em que cada elemento é um par que tem uma chave de classificação cujo valor é único, bem como um valor de dados associado.|
|[Classe hash_multimap](hash-multimap-class.md)|Usado para o armazenamento e a recuperação rápida de dados de uma coleção em que cada elemento é um par que tem uma chave de classificação cujo valor não precisa ser único e ser um valor de dados associado.|

## <a name="requirements"></a>Requisitos

**Cabeçalho:** \<hash_map>

**Namespace:** stdext

## <a name="see-also"></a>Consulte também

[Referência de Arquivos de Cabeçalho](cpp-standard-library-header-files.md)<br/>
[Acesso Thread-Safe na Biblioteca Padrão C++](thread-safety-in-the-cpp-standard-library.md)<br/>
[Referência da biblioteca padrão C++](cpp-standard-library-reference.md)
