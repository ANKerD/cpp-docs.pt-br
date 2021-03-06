---
title: Restrições em manipuladores de término | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ab3e361fb8d1c0478ec019a9ed0a6ea4fec704e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059934"
---
# <a name="restrictions-on-termination-handlers"></a>Restrições em manipuladores de término

Não é possível usar um **goto** instrução para ir diretamente para um **Try** bloco de instrução ou uma **Finally** bloco de instrução. Em vez disso, você deve digitar o bloco de instruções por meio do fluxo de controle normal. (Você pode, no entanto, ir de um **Try** bloco de instruções.) Além disso, você não pode aninhar um manipulador de exceção ou manipulador de encerramento dentro de um **Finally** bloco.

Além disso, alguns tipos de código permitidos em um manipulador de encerramento geram resultados duvidosos. Portanto, você deve usá-los com cuidado, se usá-los. Um é um **goto** instrução que ignora um **Finally** bloco de instrução. Se o bloco estiver sendo executado como parte do encerramento normal, nada incomum acontecerá. No entanto, se o sistema estiver desenrolando a pilha, esse processo será interrompido e a função atual obterá o controle como se não houvesse nenhum término anormal.

Um **retornar** instrução dentro de uma **Finally** bloco de instruções apresenta aproximadamente a mesma situação. O controle retorna ao chamador imediato da função que contém o manipulador de encerramento. Se o sistema estava desenrolando a pilha, esse processo é paralisado e o programa continua como se nenhuma exceção tivesse sido gerada.

## <a name="see-also"></a>Consulte também

[Escrevendo um manipulador de término](../cpp/writing-a-termination-handler.md)<br/>
[Tratamento de exceções estruturado (C/C++)](../cpp/structured-exception-handling-c-cpp.md)