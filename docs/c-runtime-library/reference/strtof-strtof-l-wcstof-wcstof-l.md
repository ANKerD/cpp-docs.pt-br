---
title: strtof, _strtof_l, wcstof, _wcstof_l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstof
- _tcstof_l
- stdlib/strtof
- strtof
- stdlib/_strtof_l
- _strtof_l
- corecrt_wstdlib/wcstof
- wcstof
- corecrt_wstdlib/_wcstof_l
- _wcstof_l
dev_langs:
- C++
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95db2a75d04454289b01f96680df6c5b5ab89e78
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416827"
---
# <a name="strtof-strtofl-wcstof-wcstofl"></a>strtof, _strtof_l, wcstof, _wcstof_l

Converte cadeias de caracteres para um valor de ponto flutuante de precisão simples.

## <a name="syntax"></a>Sintaxe

```C
float strtof(
   const char *strSource,
   char **endptr
);
float _strtof_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
float wcstof(
   const wchar_t *strSource,
   wchar_t **endptr
);
float wcstof_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

## <a name="parameters"></a>Parâmetros

*strSource*<br/>
Cadeia de caracteres terminada em nulo a ser convertida.

*endptr*<br/>
Ponteiro para o caractere que interrompe o exame.

*locale*<br/>
A localidade a ser usada.

## <a name="return-value"></a>Valor de retorno

**strtof** retorna o valor do número de ponto flutuante, exceto quando a representação causaria um estouro, nesse caso, a função retorna + /-**HUGE_VALF**. O sinal de **HUGE_VALF** coincide com o sinal do valor que não pode ser representado. **strtof** retorna 0 se nenhuma conversão pode ser executada ou ocorrerá um estouro negativo.

**wcstof** retorna valores de maneira semelhante para **strtof**. Para ambas as funções, **errno** é definido como **ERANGE** se ocorre estouro ou estouro negativo e o manipulador de parâmetro inválido é invocado, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md).

Para obter mais informações sobre os códigos de retorno, consulte [errno, _doserrno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Comentários

Cada função converte a cadeia de caracteres de entrada *strSource* para um **float**. O **strtof** função converte *strSource* para um valor de precisão única. **strtof** para de ler a cadeia de caracteres *strSource* no primeiro caractere que não reconhece como parte de um número. Este pode ser o caractere nulo de terminação. **wcstof** é uma versão de caractere largo de **strtof**; seu *strSource* argumento é uma cadeia de caracteres largos. Caso contrário, essas funções se comportam de forma idêntica.

### <a name="generic-text-routine-mappings"></a>Mapeamentos da rotina de texto genérico

|Rotina TCHAR.H|_UNICODE e _MBCS não definidos|_MBCS definido|_UNICODE definido|
|---------------------|------------------------------------|--------------------|-----------------------|
|**tcstof**|**strtof**|**strtof**|**wcstof**|
|**tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

O **LC_NUMERIC** categoria determina da localidade atual do caractere base no reconhecimento de *strSource*; para obter mais informações, consulte [setlocale, wsetlocale](setlocale-wsetlocale.md). As funções que não têm o **_l** sufixo usam a localidade atual; aqueles que têm o sufixo são idênticas, exceto que eles usam a localidade que é transmitida em vez disso. Para obter mais informações, consulte [Localidade](../../c-runtime-library/locale.md).

Se *endptr* não é **nulo**, um ponteiro para o caractere que interrompeu a verificação é armazenado no local que é apontado pelo *endptr*. Se nenhuma conversão pode ser executada (sem dígitos válidos foram encontrados ou uma base inválida foi especificada), o valor de *strSource* é armazenado no local que é apontado pelo *endptr*.

**strtof** espera *strSource* para apontar para uma cadeia de caracteres da seguinte forma:

[*espaço em branco*] [*sinal*] [*dígitos*] [__.__ *dígitos*] [{**e** &#124; **E**} [*sinal*] *dígitos*]

Um *espaço em branco* pode consistir em caracteres de espaço e tabulação, que são ignorados; *sinal* é plus (**+**) ou sinal de subtração (**-**); e *dígitos* são um ou mais dígitos decimais. Se nenhum dígito aparecer antes do caractere fracionário, pelo menos um deverá aparecer após o caractere fracionário. Os dígitos decimais podem ser seguidos por um expoente, que consiste em uma carta de apresentação (**e** ou **E**) e, opcionalmente, inteiro. Se nem um expoente nem um caractere fracionário aparecer, supõe-se que um caractere fracionário siga o último dígito na cadeia de caracteres. O primeiro caractere que não é adequado a esse formato interrompe o exame.

As versões UCRT dessas funções não dão suporte à conversão de estilo Fortran (**d** ou **D**) letras expoente. Essa extensão não padrão tinha suporte em versões anteriores do CRT e pode ser uma alteração significativa para seu código.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**strtof**, **strtof_l**|C: \<stdlib.h> C++: &lt;cstdlib> ou \<stdlib.h>|
|**wcstof**, **wcstof_l**|C: \<stdlib.h> ou \<wchar.h> C++: &lt;cstdlib>, \<stdlib.h> ou \<wchar.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_strtof.c
// This program uses strtof to convert a
// string to a single-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   float x;

   string = "3.14159This stopped it";
   x = strtof(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtof = %f\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.14159This stopped it
   strtof = 3.141590
   Stopped scan at: This stopped it
```

## <a name="see-also"></a>Consulte também

[Conversão de Dados](../../c-runtime-library/data-conversion.md)<br/>
[Suporte a ponto flutuante](../../c-runtime-library/floating-point-support.md)<br/>
[Interpretação de sequências de caracteres multibyte](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Localidade](../../c-runtime-library/locale.md)<br/>
[Funções de valor de cadeia de caracteres para numérico](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
