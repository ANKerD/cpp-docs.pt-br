---
title: _chsize | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _chsize
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _chsize
dev_langs:
- C++
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb40d218439ebe308e7d7cf01ab5043a2ebb3b1e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395748"
---
# <a name="chsize"></a>_chsize

Altera o tamanho de um arquivo. Uma versão mais segura está disponível; consulte [_chsize_s](chsize-s.md).

## <a name="syntax"></a>Sintaxe

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>Parâmetros

*fd*<br/>
Descritor de arquivo que faz referência a um arquivo aberto.

*size*<br/>
Novo tamanho do arquivo em bytes.

## <a name="return-value"></a>Valor de retorno

**chsize** retorna o valor 0 se o tamanho do arquivo é alterado com êxito. Um valor de retorno de -1 indica um erro: **errno** é definido como **EACCES** se o arquivo especificado é somente leitura ou o arquivo especificado está bloqueado contra o acesso, para **EBADF** se a descritor é inválido, **ENOSPC** se nenhum espaço é deixado no dispositivo, ou **EINVAL** se *tamanho* é menor que zero.

Consulte [_doserrno, errno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) para obter mais informações sobre esses e outros códigos de retorno.

## <a name="remarks"></a>Comentários

O **chsize** função estende ou trunca o arquivo associado *fd* para o comprimento especificado por *tamanho*. O arquivo deve ser aberto em um modo que permita gravação. Caracteres nulos ('\0') que serão acrescentados se o arquivo for estendido. Se o arquivo for truncado, todos os dados do final do arquivo reduzido para o tamanho original do arquivo serão perdidos.

Essa função valida seus parâmetros. Se *tamanho* é menor que zero ou *fd* é um descritor de arquivo inválido, o manipulador de parâmetro inválido é invocado, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md).

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|Cabeçalho opcional|
|-------------|---------------------|---------------------|
|**_chsize**|\<io.h>|\<errno.h>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_chsize.c
// This program uses _filelength to report the size
// of a file before and after modifying it with _chsize.

#include <io.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh, result;
   unsigned int nbytes = BUFSIZ;

   // Open a file
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,
                 _S_IREAD | _S_IWRITE ) == 0 )
   {
      printf( "File length before: %ld\n", _filelength( fh ) );
      if( ( result = _chsize( fh, 329678 ) ) == 0 )
         printf( "Size successfully changed\n" );
      else
         printf( "Problem in changing the size\n" );
      printf( "File length after:  %ld\n", _filelength( fh ) );
      _close( fh );
   }
}
```

```Output
File length before: 0
Size successfully changed
File length after:  329678
```

## <a name="see-also"></a>Consulte também

[Manipulação de Arquivos](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
