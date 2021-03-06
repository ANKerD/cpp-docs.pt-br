---
title: Limites do compilador | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76b08ab88ce5487485c8b8872488c0cf784ad2c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093539"
---
# <a name="compiler-limits"></a>Limites do compilador

O padrão do C++ recomenda limites para várias construções de linguagem. A lista a seguir contém casos onde o compilador do Visual C++ não implementa os limites recomendados. O primeiro número é o limite estabelecido no padrão ISO C++11 (INCITS/ISO/IEC 14882-2011[2012], Anexo B) e o segundo número é o limite implementado pelo Visual C++:

- Níveis de aninhamento de instruções compostas, estruturas de controle de iteração e seleção de controlam estruturas - padrão C++: 256, compilador do Visual C++: depende da combinação de instruções que estão aninhadas, mas geralmente entre 100 e 110.

- Parâmetros em uma definição macropadrão C++: 256, compilador do Visual C++: 127.

- Argumentos em uma invocação de macropadrão C++: 256, compilador do Visual C++ 127.

- Literal ou largo sequência de caracteres literal de cadeia de caracteres em um caractere (depois da concatenação) - padrão do C++: 65536, compilador do Visual C++: 65535 caracteres de byte único, incluindo o terminador NULL e os caracteres de byte duplo 32767, incluindo o terminador NULL.

- Níveis de classe aninhada, estrutura ou união definições em um único `struct-declaration-list` -padrão do C++: 256, compilador do Visual C++: 16.

- Inicializadores de membro em uma definição de construtor - padrão C++: 6144, compilador do Visual C++: c++:6144.

- Qualificações do escopo de um identificador - padrão C++: 256, compilador do Visual C++: 127.

- Aninhado **extern** especificações - padrão C++: 1024, o compilador do Visual C++: 9 (sem contar o implícita **extern** especificação no escopo global ou 10, se você contar implícito **extern**  especificação no escopo global...

- Argumentos do modelo em uma declaração de modelo – o padrão C++: 1024, o compilador do Visual C++: 2046.

## <a name="see-also"></a>Consulte também

[Comportamento não padrão](../cpp/nonstandard-behavior.md)