---
title: Usando símbolos de C ou C++ em blocos ASM | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ba8426e2a7ae1152a41fafa0c239498801c6e4d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678887"
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>Usando símbolos de C ou C++ em blocos __asm

**Seção específica da Microsoft**

Um `__asm` bloco pode se referir a qualquer símbolo de C ou C++ no escopo em que o bloco é exibido. (Símbolos de C e C++ são nomes de variáveis, nomes de função e rótulos; que é, nomes que não são constantes simbólicas ou `enum` membros. Você não pode chamar o membro de C++ funções.)

Algumas restrições se aplicam ao uso de símbolos de C e C++:

- Cada instrução de linguagem de assembly pode conter apenas um C ou o símbolo de C++. Vários símbolos podem aparecer na instrução de montagem somente com **comprimento**, **tipo**, e **tamanho** expressões.

- Funções referenciadas em um `__asm` bloco deve ser declarado (com protótipo) anteriormente no programa. Caso contrário, o compilador não pode distinguir entre os nomes de função e rótulos no `__asm` bloco.

- Um `__asm` bloco não pode usar quaisquer símbolos de C ou C++ com a mesma ortografia como palavras MASM reservada (independentemente do caso). Palavras reservada de MASM incluem nomes de instrução, como **PUSH** e registrar nomes como SI.

- Marcas de estrutura e união não são reconhecidas na `__asm` blocos.

**Fim da seção específica da Microsoft**

## <a name="see-also"></a>Consulte também

[Usando C ou C++ em blocos __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>