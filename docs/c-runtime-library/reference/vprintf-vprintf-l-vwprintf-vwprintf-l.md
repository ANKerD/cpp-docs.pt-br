---
title: vprintf, _vprintf_l, vwprintf, _vwprintf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- vprintf
- _vwprintf_l
- _vprintf_l
- vwprintf
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
- vwprintf
- _vtprintf
dev_langs:
- C++
helpviewer_keywords:
- vwprintf function
- _vwprintf_l function
- vwprintf_l function
- _vtprintf function
- vtprintf_l function
- vprintf function
- _vprintf_l function
- vprintf_l function
- vtprintf function
- _vtprintf_l function
- formatted text [C++]
ms.assetid: 44549505-00a0-4fa7-9a85-f2e666f55a38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cf6a20c3153c8769e83cab35ab5196bd629bef7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197843"
---
# <a name="vprintf-vprintfl-vwprintf-vwprintfl"></a>vprintf, _vprintf_l, vwprintf, _vwprintf_l

Grava saída formatada usando um ponteiro para uma lista de argumentos. Versões mais seguras dessas funções estão disponíveis, consulte [vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md).

## <a name="syntax"></a>Sintaxe

```C
int vprintf(
   const char *format,
   va_list argptr
);
int _vprintf_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int vwprintf(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parâmetros

*format*<br/>
Especificação de formato.

*argptr*<br/>
Ponteiro para a lista de argumentos.

*locale*<br/>
A localidade a ser usada.

Para obter mais informações, consulte [Especificações de formato](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Valor de retorno

**vprintf** e **vwprintf** retornar o número de caracteres gravados, não incluindo o caractere nulo de terminação ou um valor negativo se ocorrer um erro de saída. Se *formato* for um ponteiro nulo ou se a cadeia de caracteres de formato contiver caracteres de formatação inválidos, o manipulador de parâmetro inválido será invocado, conforme descrito em [validação de parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução puder continuar, as funções retornarão -1 e defina **errno** à **EINVAL**.

Para obter informações sobre esses e outros códigos de erro, consulte [_doserrno, errno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Comentários

Cada uma dessas funções usa um ponteiro para uma lista de argumentos, em seguida, formata e grava os dados fornecidos no **stdout**.

**vwprintf** é a versão de caractere largo de **vprintf**; as duas funções terão comportamento idêntico se o fluxo for aberto no modo ANSI. **vprintf** atualmente, não suporta a saída em um fluxo UNICODE.

As versões dessas funções com o **l** sufixo são idênticas, exceto que eles usam o parâmetro de localidade passado em vez da localidade do thread atual.

> [!IMPORTANT]
> Verifique se *format* não é uma cadeia de caracteres definida pelo usuário. Para obter mais informações, consulte [Avoiding Buffer Overruns](/windows/desktop/SecBP/avoiding-buffer-overruns) (Evitando estouros de buffer). Observe que as cadeias de caracteres de formato inválido são detectadas e resultará em um erro.

### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico

|Rotina TCHAR.H|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|
|---------------------|------------------------------------|--------------------|-----------------------|
|**vtprintf**|**vprintf**|**vprintf**|**vwprintf**|
|**vtprintf_l**|**_vprintf_l**|**_vprintf_l**|**_vwprintf_l**|

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|Cabeçalhos opcionais|
|-------------|---------------------|----------------------|
|**vprintf**, **vprintf_l**|\<stdio.h> e \<stdarg.h>|\<varargs.h>*|
|**vwprintf**, **vwprintf_l**|\<stdio.h> ou \<wchar.h> e \<stdarg.h>|\<varargs.h>*|

\* Necessário para compatibilidade com UNIX V.

Não há suporte para o console em aplicativos da plataforma Universal do Windows (UWP). Os identificadores de fluxo padrão que estão associados com o console **stdin**, **stdout**, e **stderr**, deverá ser redirecionado para funções de tempo de execução C possam ser usados em aplicativos UWP . Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[E/S de fluxo](../../c-runtime-library/stream-i-o.md)<br/>
[Funções vprintf](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
