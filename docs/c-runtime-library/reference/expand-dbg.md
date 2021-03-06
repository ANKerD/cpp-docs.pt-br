---
title: _expand_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _expand_dbg
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- expand_dbg
- _expand_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 023bda761454a6a1e18ce68c8e7576af2759abbf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403629"
---
# <a name="expanddbg"></a>_expand_dbg

Redimensiona um bloco especificado de memória no heap pela expansão ou contração do bloco (somente versão de depuração).

## <a name="syntax"></a>Sintaxe

```C
void *_expand_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parâmetros

*Dados do usuário*<br/>
Ponteiro para o bloco de memória alocado anteriormente.

*newSize*<br/>
Solicitou o novo tamanho do bloco (em bytes).

*blockType*<br/>
Tipo de bloco redimensionado solicitado: **client_block** ou **normal_block**.

*filename*<br/>
Ponteiro para o nome do arquivo de origem que solicitou expandir operação ou **nulo**.

*linenumber*<br/>
Número no arquivo de origem em que a operação de expansão foi solicitada da linha ou **nulo**.

O *filename* e *linenumber* parâmetros estão disponíveis somente quando **expand_dbg** foi chamado explicitamente ou [crtdbg_map_alloc](../../c-runtime-library/crtdbg-map-alloc.md)constante de pré-processador foi definido.

## <a name="return-value"></a>Valor de retorno

Após a conclusão bem-sucedida, **expand_dbg** retorna um ponteiro para o bloco de memória redimensionado. Como a memória não é movida, o endereço é o mesmo que userData. Se ocorreu um erro ou o bloco não foi possível expandir o tamanho solicitado, ele retorna **nulo**. Se ocorrer uma falha, **errno** com informações do sistema operacional sobre a natureza da falha. Para obter mais informações sobre **errno**, consulte [errno, doserrno, sys_errlist e sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Comentários

O **expand_dbg** função é uma versão de depuração no _[expanda](expand.md) função. Quando [Debug](../../c-runtime-library/debug.md) não está definida, cada chamada para **expand_dbg** é reduzido para uma chamada para **expandir**. Ambos **expandir** e **expand_dbg** redimensionar um bloco de memória no heap de base, mas **expand_dbg** acomoda a vários recursos de depuração: buffers em ambos os lados do usuário parte do bloco para testar vazamentos, um parâmetro de tipo de bloco para rastrear tipos específicos de alocação, e *filename*/*linenumber* informações para determinar a origem do solicitações de alocação.

**expand_dbg** redimensiona o bloco de memória especificado com um pouco mais espaço do que o solicitado *newSize*. *newSize* pode ser maior ou menor que o tamanho do bloco de memória alocada originalmente. O espaço adicional é usado pelo gerenciador de heaps de depuração para vincular os blocos de memória de depuração e fornecer informações do cabeçalho de depuração ao aplicativo e substituir buffers. O redimensionamento é realizado pela expansão ou contração do bloco de memória original. **expand_dbg** não move o bloco de memória, como faz o [realloc_dbg](realloc-dbg.md) função.

Quando *newSize* for maior do que o bloco original tamanho, o bloco de memória é expandido. Durante uma expansão, se o bloco de memória não pode ser expandido para acomodar o tamanho solicitado, **nulo** é retornado. Quando *newSize* é menor do que o bloco original tamanho, o bloco de memória é reduzido até que o novo tamanho seja obtido.

Para obter informações sobre como os blocos de memória são alocados, inicializados e gerenciados na versão de depuração do heap de base, consulte [Detalhes do heap de depuração CRT](/visualstudio/debugger/crt-debug-heap-details). Para obter informações sobre os tipos de blocos de alocação e como eles são usados, consulte [Types of blocks on the debug heap](/visualstudio/debugger/crt-debug-heap-details) (Tipos de blocos no heap de depuração). Para obter informações sobre as diferenças entre chamar uma função de heap padrão e sua versão de depuração em um build de depuração de um aplicativo, consulte [Versões de depuração das funções de alocação de heap](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Essa função valida seus parâmetros. Se *memblock* é um ponteiro nulo, ou se o tamanho for maior do que **heap_maxreq**, esta função chama um manipulador de parâmetro inválido, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução é permitida para continuar, **errno** é definido como **EINVAL** e a função retorna **nulo**.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Libraries

Somente versões de depuração de [bibliotecas de tempo de execução C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Exemplo

```C
// crt_expand_dbg.c
//
// This program allocates a block of memory using _malloc_dbg
// and then calls _msize_dbg to display the size of that block.
// Next, it uses _expand_dbg to expand the amount of
// memory used by the buffer and then calls _msize_dbg again to
// display the new amount of memory allocated to the buffer.
//

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   long *buffer;
   size_t size;

   // Call _malloc_dbg to include the filename and line number
   // of our allocation request in the header
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );
   if( buffer == NULL )
      exit( 1 );

   // Get the size of the buffer by calling _msize_dbg
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

   // Expand the buffer using _expand_dbg and show the new size
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );

   if( buffer == NULL )
      exit( 1 );
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",
           size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _expand_dbg of 1 more long: 164
```

## <a name="comment"></a>Comentário

A saída desse programa depende da capacidade do seu computador de expandir todas as seções. Se todas as seções estiverem expandidas, a saída será refletida na seção de saída.

## <a name="see-also"></a>Consulte também

[Rotinas de depuração](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
