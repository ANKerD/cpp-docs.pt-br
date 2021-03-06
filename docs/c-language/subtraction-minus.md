---
title: Subtração (-) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b09683592ca7fe897c8477a17c14fbc72d11f7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079954"
---
# <a name="subtraction--"></a>Subtração (-)

O operador de subtração (**-**) subtrai o segundo operando do primeiro. Ambos os operandos podem ser do tipo integral ou flutuante, ou um operando pode ser um ponteiro e o outro um inteiro.

Quando dois ponteiros são subtraídos, a diferença é convertida em um valor integral assinado dividindo a diferença pelo tamanho de um valor do tipo que os ponteiros indicam. O tamanho do valor integral é definido pelo tipo **ptrdiff_t** no arquivo STDDEF.H de inclusão padrão. O resultado representa o número de posições de memória desse tipo entre os dois endereços. O resultado é garantido somente para ser significativo para dois elementos da mesma matriz, como discutido em [Aritmética do ponteiro](../c-language/pointer-arithmetic.md).

Quando um valor inteiro é subtraído de um valor de ponteiro, o operador de subtração converte o valor do inteiro (*i*) multiplicando-o pelo tamanho do valor que o ponteiro indica. Após a conversão, o valor de inteiro representa as posições de memória *i*, no qual cada posição tem o comprimento especificado pelo tipo de ponteiro. Quando o valor do inteiro convertido é subtraído do valor do ponteiro, como resultado, o endereço de memória *i* se posiciona antes do endereço original. O novo ponteiro aponta para um valor do tipo indicado pelo valor do ponteiro original.

## <a name="see-also"></a>Consulte também

[Operadores aditivos C](../c-language/c-additive-operators.md)