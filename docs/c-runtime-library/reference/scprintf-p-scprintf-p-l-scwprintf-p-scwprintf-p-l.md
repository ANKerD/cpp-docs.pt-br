---
title: _scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _scwprintf_p
- _scprintf_p_l
- _scwprintf_p_l
- _scprintf_p
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
- _scwprintf_p_l
- _sctprintf_p
- scprintf_p_l
- scprintf_p
- _sctprintf_p_l
- scwprintf_p
- _scprintf_p_l
- scwprintf_p_l
- _scprintf_p
- _scwprintf_p
dev_langs:
- C++
helpviewer_keywords:
- sctprintf_p_l function
- _scwprintf_p_l function
- scprintf_p_l function
- _scprintf_p function
- _scprintf_p_l function
- scprintf_p function
- sctprintf_p function
- _scwprintf_p function
- _sctprintf_p function
- scwprintf_p function
- scwprintf_p_l function
- _sctprintf_p_l function
ms.assetid: 8390d1e1-2826-47a4-851f-6635a88087cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2120eaaee5acfa3628650b5df1f03448ee282a91
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407178"
---
# <a name="scprintfp-scprintfpl-scwprintfp-scwprintfpl"></a>_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l

Retorna o número de caracteres na cadeia de caracteres formatada, com a capacidade de especificar a ordem na qual os parâmetros são usados na cadeia de caracteres de formato.

## <a name="syntax"></a>Sintaxe

```C
int _scprintf_p(
   const char *format [,
   argument] ...
);
int _scprintf_p_l(
   const char *format,
   locale_t locale [,
   argument] ...
);
int _scwprintf_p (
   const wchar_t *format [,
   argument] ...
);
int _scwprintf_p _l(
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parâmetros

*format*<br/>
Cadeia de caracteres de controle de formato.

*argument*<br/>
Argumentos opcionais.

*locale*<br/>
A localidade a ser usada.

## <a name="return-value"></a>Valor de retorno

Retorna o número de caracteres que será gerado se a cadeia de caracteres for impressa ou enviada para um arquivo ou o buffer usando os códigos de formatação especificados. O valor retornado não inclui o caractere nulo de terminação. **scwprintf_p** executa a mesma função para caracteres largos.

A diferença entre **scprintf_p** e **scprintf** é que **scprintf_p** oferece suporte a parâmetros de posição, que permite especificar a ordem em que os argumentos são usados na cadeia de caracteres de formato. Para obter mais informações, consulte [Parâmetros posicionais printf_p](../../c-runtime-library/printf-p-positional-parameters.md).

Se *formato* é um **nulo** ponteiro, o manipulador de parâmetro inválido é invocado, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução é permitida para continuar, essas funções retornam -1 e defina **errno** para **EINVAL**.

Para obter informações sobre esses e outros códigos de erro, consulte [_doserrno, errno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Comentários

Cada *argumento* (se houver) é convertido de acordo com a especificação de formato correspondente em *formato*. O formato consiste em caracteres simples e tem o mesmo formulário e funcionar como o *formato* argumento [printf](printf-printf-l-wprintf-wprintf-l.md).

As versões dessas funções com o **_l** sufixo são idênticas, exceto que eles usam o parâmetro de localidade passado em vez da localidade do thread atual.

> [!IMPORTANT]
> Verifique se *format* não é uma cadeia de caracteres definida pelo usuário.

### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico

|Rotina Tchar.h|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**sctprintf_p**|**_scprintf_p**|**_scprintf_p**|**_scwprintf_p**|
|**sctprintf_p_l**|**_scprintf_p_l**|**_scprintf_p_l**|**_scwprintf_p_l**|

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**scprintf_p**, **scprintf_p_l**|\<stdio.h>|
|**scwprintf_p**, **scwprintf_p_l**|\<stdio.h> ou \<wchar.h>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[E/S de fluxo](../../c-runtime-library/stream-i-o.md)<br/>
[_scprintf, _scprintf_l, _scwprintf, _scwprintf_l](scprintf-scprintf-l-scwprintf-scwprintf-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
