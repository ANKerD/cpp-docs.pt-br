---
title: '&lt;memory&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::<memory>
- <memory>
- std::<memory>
dev_langs:
- C++
helpviewer_keywords:
- memory header
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b90a96816855e08610d0f63f3ab5c237d564453
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217943"
---
# <a name="ltmemorygt"></a>&lt;memory&gt;

Define uma classe, um operador e vários modelos que ajudam a alocar e a liberar objetos.

## <a name="syntax"></a>Sintaxe

```cpp
#include <memory>

```

## <a name="members"></a>Membros

### <a name="functions"></a>Funções

|Função|Descrição|
|-|-|
|[addressof](../standard-library/memory-functions.md#addressof)|Obtém o endereço verdadeiro de um objeto.|
|[align](../standard-library/memory-functions.md#align)|Retorna um ponteiro para um intervalo de um determinado tamanho, com base no endereço de início e alinhamento fornecidos.|
|[allocate_shared](../standard-library/memory-functions.md#allocate_shared)|Cria um `shared_ptr` para objetos atribuídos e construídos para um determinado tipo com um alocador especificado.|
|[const_pointer_cast](../standard-library/memory-functions.md#const_pointer_cast)|Conversão constante para `shared_ptr`.|
|[declare_no_pointers](../standard-library/memory-functions.md#declare_no_pointers)|Informa a um coletor de lixo que os caracteres começando em um endereço especificado e recaindo no tamanho de bloco indicado não contêm ponteiros rastreáveis.|
|[declare_reachable](../standard-library/memory-functions.md#declare_reachable)|Informa a coleta de lixo que o endereço indicado é para armazenamento alocado e é alcançável.|
|[default_delete](../standard-library/memory-functions.md#default_delete)|Exclui objetos alocados com `operator new`. Adequado para uso com `unique_ptr`.|
|[dynamic_pointer_cast](../standard-library/memory-functions.md#dynamic_pointer_cast)|Conversão dinâmica para `shared_ptr`.|
|[get_deleter](../standard-library/memory-functions.md#get_deleter)|Obtenha o deletor de `shared_ptr`.|
|[get_pointer_safety](../standard-library/memory-functions.md#get_pointer_safety)|Retorna o tipo de segurança do ponteiro pressuposto por qualquer coletor de lixo.|
|[get_temporary_buffer](../standard-library/memory-functions.md#get_temporary_buffer)|Atribui o armazenamento temporário para uma sequência de elementos que não excede um número especificado de elementos.|
|[make_shared](../standard-library/memory-functions.md#make_shared)|Cria e retorna um `shared_ptr` que aponta para o objeto alocado construído do zero ou mais argumentos usando o alocador padrão.|
|[make_unique](../standard-library/memory-functions.md#make_unique)|Cria e retorna um [unique_ptr](../standard-library/unique-ptr-class.md) que aponta para o objeto alocado construído de zero ou mais argumentos.|
|[owner_less](../standard-library/memory-functions.md#owner_less)|Permite comparações mistas baseadas em propriedade de ponteiros compartilhados e fracos.|
|[pointer_safety](../standard-library/memory-enums.md#pointer_safety)|Uma enumeração de todos os possíveis valores de retorno para `get_pointer_safety`.|
|[return_temporary_buffer](../standard-library/memory-functions.md#return_temporary_buffer)|Desaloca a memória temporária que foi alocada usando a função de modelo `get_temporary_buffer`.|
|[static_pointer_cast](../standard-library/memory-functions.md#static_pointer_cast)|Conversão estática para `shared_ptr`.|
|[swap](../standard-library/memory-functions.md#swap)|Troca dois objetos `shared_ptr` ou `weak_ptr`.|
|[undeclare_no_pointers](../standard-library/memory-functions.md#undeclare_no_pointers)|Informa um coletor de lixo que os caracteres no bloco de memória definido por um ponteiro de endereço básico e o tamanho de bloco agora podem conter ponteiros rastreáveis.|
|[undeclare_reachable](../standard-library/memory-functions.md#undeclare_reachable)|Informa um `garbage_collector` que um local de memória especificado não é alcançável.|
|[uninitialized_copy](../standard-library/memory-functions.md#uninitialized_copy)|Copia objetos de um intervalo de entrada especificado em um intervalo de destino não inicializado.|
|[uninitialized_copy_n](../standard-library/memory-functions.md#uninitialized_copy_n)|Cria uma cópia de um número especificado de elementos de um iterador de entrada. As cópias são colocadas em um iterador de avanço.|
|[uninitialized_fill](../standard-library/memory-functions.md#uninitialized_fill)|Copia objetos de um valor especificado em um intervalo de destino não inicializado.|
|[uninitialized_fill_n](../standard-library/memory-functions.md#uninitialized_fill_n)|Copia objetos de um valor especificado em um número especificado de elementos de um intervalo de destino não inicializado.|

### <a name="operators"></a>Operadores

|Operador|Descrição|
|-|-|
|[operator!=](../standard-library/memory-operators.md#op_neq)|Testa a desigualdade entre objetos do alocador de uma classe especificada.|
|[operator==](../standard-library/memory-operators.md#op_eq_eq)|Testa a igualdade entre objetos do alocador de uma classe especificada.|
|[operator>=](../standard-library/memory-operators.md#op_gt_eq)|Testa um objeto do alocador que é maior ou igual a um segundo objeto do alocador de uma classe especificada.|
|[operator<](../standard-library/memory-operators.md#op_lt)|Testa um objeto que é menor que um segundo objeto de uma classe especificada.|
|[operator\<=](../standard-library/memory-operators.md#op_gt_eq)|Testa um objeto que é menor ou igual a um segundo objeto de uma classe especificada.|
|[operator>](../standard-library/memory-operators.md#op_gt)|Testa um objeto que é maior que um segundo objeto de uma classe especificada.|
|[operator<<](../standard-library/memory-operators.md#op_lt_lt)|Inserção de `shared_ptr`.|

### <a name="classes"></a>Classes

|Classe|Descrição|
|-|-|
|[allocator](../standard-library/allocator-class.md)|A classe de modelo descreve um objeto que gerencia a alocação de armazenamento e a liberação de matrizes de objetos do tipo **Type**.|
|[allocator_traits](../standard-library/allocator-traits-class.md)|Descreve um objeto que determina todas as informações necessárias a um contêiner habilitado para alocador.|
|[auto_ptr](../standard-library/auto-ptr-class.md)|A classe de modelo descreve um objeto que armazena um ponteiro para um objeto alocado do tipo **tipo** <strong>\*</strong> que garante que o objeto para o qual ele aponta é excluído quando seu auto_ptr delimitador obtém destruído.|
|[bad_weak_ptr](../standard-library/bad-weak-ptr-class.md)|Relata a exceção weak_ptr incorreta.|
|[enabled_shared_from_this](../standard-library/enable-shared-from-this-class.md)|Ajuda a gerar um `shared_ptr`.|
|[pointer_traits](../standard-library/pointer-traits-struct.md)|Fornece informações que são necessárias a um objeto da classe de modelo `allocator_traits` para descrever um alocador com o tipo de ponteiro `Ptr`.|
|[raw_storage_iterator](../standard-library/raw-storage-iterator-class.md)|Uma classe de adaptador que é fornecida para permitir que algoritmos armazenem seus resultados na memória não inicializada.|
|[shared_ptr](../standard-library/shared-ptr-class.md)|Encapsula um ponteiro inteligente de contagem de referência em torno de um objeto alocado dinamicamente.|
|[unique_ptr](../standard-library/unique-ptr-class.md)|Armazena um ponteiro para um objeto possuído. O ponteiro não é possuído por nenhum outro `unique_ptr`. O `unique_ptr` é destruído quando o proprietário é destruído.|
|[weak_ptr](../standard-library/weak-ptr-class.md)|Encapsula um ponteiro vinculado de modo fraco.|

### <a name="specializations"></a>Especializações

|||
|-|-|
|[allocator\<void>](../standard-library/allocator-void-class.md)|Uma especialização do alocador de classe de modelo para o tipo void, definindo os únicos tipos de membro que fazem sentido neste contexto especializado.|

## <a name="see-also"></a>Consulte também

[Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)<br/>
[Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
