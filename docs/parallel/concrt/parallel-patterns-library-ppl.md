---
title: Parallel Patterns Library (PPL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Parallel Patterns Library (PPL)
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2bbed984f20c01544a972317f787a00abf6c7b94
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382525"
---
# <a name="parallel-patterns-library-ppl"></a>Biblioteca de padrões paralelos (PPL)

A biblioteca de padrões paralelos (PPL) fornece um modelo de programação imperativo que promove a escalabilidade e a facilidade de uso para o desenvolvimento de aplicativos simultâneos. O PPL baseia-se os componentes de gerenciamento de recursos e agendamento de tempo de execução de simultaneidade. Ele aumenta o nível de abstração entre o código do aplicativo e o mecanismo subjacente de threading, fornecendo algoritmos genéricos, fortemente tipada e contêineres que atuam em dados em paralelo. O PPL também permite que você desenvolva aplicativos dimensionáveis ao fornecer alternativas para estado compartilhado.

O PPL fornece os seguintes recursos:

- *Paralelismo de tarefas*: um mecanismo que funciona sobre o ThreadPool do Windows para executar vários itens de trabalho (tarefas) em paralelo

- *Algoritmos em paralelo*: algoritmos genéricos que funciona em tempo de execução de simultaneidade para atuar em coleções de dados em paralelo

- *Contêineres e objetos em paralelo*: tipos de contêiner genérico que fornecem acesso simultâneo seguro aos seus elementos

## <a name="example"></a>Exemplo

O PPL fornece um modelo de programação que se parece com a biblioteca padrão C++. O exemplo a seguir demonstra vários recursos da PPL. Ele calcula vários números de Fibonacci em série e em paralelo. Ambas as computações agir em uma [std:: array](../../standard-library/array-class-stl.md) objeto. O exemplo também imprime no console a hora em que é necessária executar ambos os cálculos.

A versão serial usa a biblioteca padrão C++ [std::for_each](../../standard-library/algorithm-functions.md#for_each) algoritmo para percorrer a matriz e armazena os resultados em um [std:: Vector](../../standard-library/vector-class.md) objeto. A versão paralela executa a mesma tarefa, mas usa a PPL [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) algoritmo e armazena os resultados em um [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) objeto. O `concurrent_vector` classe permite que cada iteração do loop simultaneamente adicionar elementos sem a necessidade de sincronizar o acesso de gravação ao contêiner.

Porque `parallel_for_each` age simultaneamente, a versão paralela deste exemplo deve classificar o `concurrent_vector` objeto para produzir os mesmos resultados que a versão serial.

Observe que o exemplo usa um método simples para calcular os números de Fibonacci; No entanto, esse método ilustra como o tempo de execução de simultaneidade pode melhorar o desempenho de computações longas.

[!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/cpp/parallel-patterns-library-ppl_1.cpp)]

A saída de exemplo a seguir é para um computador com quatro processadores.

```Output
serial time: 9250 ms
parallel time: 5726 ms

fib(24): 46368
fib(26): 121393
fib(41): 165580141
fib(42): 267914296
```

Cada iteração do loop requer uma quantidade diferente de tempo para ser concluída. O desempenho de `parallel_for_each` está limitada a operação que termina pela última vez. Portanto, você não deve esperar melhorias de desempenho linear entre as versões seriais e paralelas deste exemplo.

## <a name="related-topics"></a>Tópicos relacionados

|Título|Descrição|
|-----------|-----------------|
|[Paralelismo de tarefas](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|Descreve a função de tarefas e grupos de tarefas no PPL.|
|[Algoritmos paralelos](../../parallel/concrt/parallel-algorithms.md)|Descreve como usar os algoritmos paralelos, como `parallel_for` e `parallel_for_each`.|
|[Contêineres e objetos em paralelo](../../parallel/concrt/parallel-containers-and-objects.md)|Descreve os vários contêineres em paralelo e objetos que são fornecidos da PPL.|
|[Cancelamento no PPL](cancellation-in-the-ppl.md)|Explica como cancelar o trabalho que está sendo executado por um algoritmo paralelo.|
|[Tempo de Execução de Simultaneidade](../../parallel/concrt/concurrency-runtime.md)|Descreve o tempo de execução de simultaneidade, que simplifica a programação paralela e contém links para tópicos relacionados.|

