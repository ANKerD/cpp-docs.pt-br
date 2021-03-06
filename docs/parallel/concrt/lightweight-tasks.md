---
title: Tarefas leves | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2d7624ce66513bd1447bc264e6c6cc29eab940c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409084"
---
# <a name="lightweight-tasks"></a>Tarefas Leves

Este documento descreve a função de tarefas leves no tempo de execução de simultaneidade. Um *tarefa leve* é uma tarefa agendada diretamente de um `concurrency::Scheduler` ou `concurrency::ScheduleGroup` objeto. A função que você fornece à API do Windows é semelhante a uma tarefa leve [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) função. Portanto, as tarefas leves são úteis quando você adaptar o código existente para usar a funcionalidade de agendamento de tempo de execução de simultaneidade. O tempo de execução de simultaneidade em si usa tarefas leves para agendar a agentes assíncronos e enviar mensagens entre blocos de mensagens assíncronos.

> [!TIP]
>  O tempo de execução de simultaneidade fornece um agendador padrão e, portanto, não é necessário criá-lo em seu aplicativo. Como o Agendador de tarefas Ajuda você a ajustar o desempenho de seus aplicativos, é recomendável que você comece com o [biblioteca de padrões paralelos (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) ou o [biblioteca de agentes assíncronos](../../parallel/concrt/asynchronous-agents-library.md) se você estiver novo no tempo de execução de simultaneidade.

Tarefas leves carregam menos sobrecarga do que os agentes assíncronos e grupos de tarefas. Por exemplo, o tempo de execução não informam quando uma tarefa leve for concluída. Além disso, o tempo de execução não capturar ou lidar com exceções que são geradas a partir de uma tarefa leve. Para obter mais informações sobre o tratamento de exceções e tarefas leves, consulte [tratamento de exceções](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).

Para a maioria das tarefas, é recomendável que você usa a funcionalidade mais robusta, como grupos de tarefas e algoritmos paralelos porque eles permitem que você mais facilmente Dividir tarefas complexas nos mais básicos. Para obter mais informações sobre grupos de tarefas, consulte [paralelismo de tarefas](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Para obter mais informações sobre os algoritmos paralelos, consulte [algoritmos paralelos](../../parallel/concrt/parallel-algorithms.md).

Para criar uma tarefa leve, chame o [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask), [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask), ou [concurrency::Scheduler::ScheduleTask ](reference/scheduler-class.md#scheduletask) método. Para aguardar uma tarefa simples terminar, aguarde até que o Agendador de pai para desligar ou usar um mecanismo de sincronização, como um [concurrency::event](../../parallel/concrt/reference/event-class.md) objeto.

## <a name="example"></a>Exemplo

Para obter um exemplo que demonstra como adaptar o código existente para usar uma tarefa leve, consulte [instruções passo a passo: adaptando o código existente para usar tarefas leves](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).

## <a name="see-also"></a>Consulte também

[Agendador de tarefas](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Instruções passo a passo: adaptando um código existente para usar tarefas leves](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)

