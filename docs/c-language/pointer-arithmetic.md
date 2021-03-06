---
title: Ponteiro aritmético | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointer arithmetic
- arithmetic pointer
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd80fd88a5924cbedf9a07ee700f16c65b66672f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020141"
---
# <a name="pointer-arithmetic"></a>Ponteiro aritmético

As operações de adição envolvendo um ponteiro e um inteiro fornecem resultados significativos apenas se o operando do ponteiro endereçar um membro de matriz e o valor inteiro produzir um deslocamento dentro dos limites da mesma matriz. Quando o valor inteiro é convertido em um deslocamento de endereço, o compilador pressupõe que somente as posições de memória do mesmo tamanho se encontram entre o endereço original e o endereço mais o deslocamento.

Esse pressuposto é válido para membros de matriz. Por definição, uma matriz é uma série de valores do mesmo tipo; seus elementos residem em locais de memória contíguos. Porém, o armazenamento para alguns tipos exceto elementos da matriz não têm garantia de preenchimento pelo mesmo tipo de identificadores. Ou seja, os espaços em branco podem aparecer entre as posições de memória, até mesmo posições do mesmo tipo. Consequentemente, os resultados da adição a ou da subtração de endereços de quaisquer valores que não os elementos da matriz serão indefinidos.

Da mesma forma, quando dois valores de ponteiro são subtraídos, a conversão pressupõe que somente valores do mesmo tipo, sem espaços em branco, se encontram entre os endereços dados pelos operandos.

## <a name="see-also"></a>Consulte também

[Operadores aditivos C](../c-language/c-additive-operators.md)