---
title: Usando VERIFY em vez de ASSERT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- assert
dev_langs:
- C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea6ea90460f3fd28724ee1fd34dfdeb3f6ae80b2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711770"
---
# <a name="using-verify-instead-of-assert"></a>Usando VERIFY em vez de ASSERT

Suponha que, quando você executa a versão de depuração do seu aplicativo do MFC, não há nenhum problema. No entanto, a versão de lançamento do mesmo aplicativo falha, retorna resultados incorretos e/ou exibe alguns outros comportamentos anormais.

Esse problema pode ser causado quando você coloca o código importantes em uma instrução ASSERT para verificar que ele seja executado corretamente. Como instruções ASSERT são comentadas na compilação de versão de um programa MFC, o código não é executado em um build de versão.

Se você estiver usando o ASSERT para confirmar que uma chamada de função foi bem-sucedida, considere o uso [VERIFY](../../mfc/reference/diagnostic-services.md#verify) em vez disso. A macro VERIFY avalia seus próprios argumentos em ambos os depuração e libere compilações do aplicativo.

Outra preferência técnica é atribuir o valor de retorno da função a uma variável temporária e, em seguida, teste a variável em uma instrução ASSERT.

Examine o seguinte fragmento de código:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Esse código é executado perfeitamente em uma versão de depuração de um aplicativo do MFC. Se a chamada para `calloc( )` falhar, uma mensagem de diagnóstico que inclui o arquivo e número de linha aparece. No entanto, em um build de varejo de um aplicativo do MFC:

- a chamada para `calloc( )` nunca ocorrer, deixando `buf` não inicializado, ou

- `strcpy_s( )` cópias "`Hello, World`" em uma parte aleatória de memória, falhando, possivelmente, o aplicativo ou fazendo com que o sistema pare de responder, ou

- `free()` tenta liberar a memória que nunca foi alocado.

Para usar ASSERT corretamente, o exemplo de código deve ser alterado para o seguinte:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );
ASSERT( buf != NULL );
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

Ou, você pode usar em vez disso, verifique se:

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>Consulte também

[Corrigindo problemas do build de versão](../../build/reference/fixing-release-build-problems.md)