---
title: Nomes de ambiente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4df255959ab1c60a5ccaeb9c4389cbcbdc56368b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081410"
---
# <a name="environment-names"></a>Nomes de ambientes

**ANSI 4.10.4.4** O conjunto de nomes de ambiente e o método para alterar a lista de ambientes usada pela função [getenv](../c-runtime-library/reference/getenv-wgetenv.md)

O conjunto de nomes de ambientes é ilimitado.

Para alterar as variáveis de ambiente de um programa C, chame a função [_putenv](../c-runtime-library/reference/putenv-wputenv.md). Para alterar as variáveis de ambiente de linha de comando no Windows, use o comando SET (por exemplo, SET LIB = D:\ LIBS).

As variáveis de ambiente definidas dentro de um programa C só existirão enquanto sua cópia do host de shell de comando do sistema operacional estiver em execução (CMD.EXE ou COMMAND.COM). Por exemplo, a linha

```
system( SET LIB = D:\LIBS );
```

executará uma cópia do shell de comando (CMD.EXE), definirá a variável de ambiente LIB e retornará ao programa C, saindo da cópia secundária de CMD.EXE. Sair dessa cópia de CMD.EXE remove a variável de ambiente temporária LIB.

Da mesma forma, as alterações feitas pela função `_putenv` durará apenas até o encerramento do programa.

## <a name="see-also"></a>Consulte também

[Funções de biblioteca](../c-language/library-functions.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)