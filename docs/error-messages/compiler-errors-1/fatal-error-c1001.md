---
title: Erro fatal C1001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1001
dev_langs:
- C++
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6363694dbd7f1a7ebfcd58cad030dfecf7f38397
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098186"
---
# <a name="fatal-error-c1001"></a>Erro fatal C1001

> INTERNO COMPILADOR ERROR(compiler file *file*, line *number*)

O compilador não pode gerar o código correto para uma construção, geralmente devido à combinação de uma expressão específica e uma opção de otimização ou um problema na análise. Se o arquivo de compilador listado tiver um utc ou segmento de caminho de C2, provavelmente é um erro de otimização. Se o arquivo tem um segmento de caminho cxxfe ou c1xx ou é msc1.cpp, provavelmente é um erro do analisador. Se o arquivo denominado cl.exe, nenhuma outra informação está disponível.

Geralmente, você pode corrigir um problema de otimização, removendo uma ou mais opções de otimização. Para determinar qual é a opção com defeito, remova uma opção em uma hora e recompile até que a mensagem de erro desaparecerá. São as opções mais comumente responsáveis [/Og (otimizações globais)](../../build/reference/og-global-optimizations.md) e [/Oi (gerar funções intrínsecas)](../../build/reference/oi-generate-intrinsic-functions.md). Depois de determinar qual opção de otimização é responsável, você pode desabilitá-lo em torno de função em que o erro ocorre usando o [otimizar](../../preprocessor/optimize.md) pragma e continuar a usar a opção para o restante do módulo. Para obter mais informações sobre opções de otimização, consulte [melhores práticas de otimização](../../build/reference/optimization-best-practices.md).

Se as otimizações não são responsáveis pelo erro, tente reescrever a linha em que o erro é relatado, ou várias linhas de código ao redor dessa linha. Para ver o código de forma que o compilador vê-lo após o pré-processamento, você pode usar o [/P (pré-processar em um arquivo)](../../build/reference/p-preprocess-to-a-file.md) opção.

Para obter mais informações sobre como isolar a origem do erro e como relatar um erro interno do compilador para a Microsoft, consulte [como relatar um problema com o conjunto de ferramentas do Visual C++](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md).