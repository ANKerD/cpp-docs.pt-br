---
title: _ismbbkpunct, _ismbbkpunct_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ismbbkpunct_l
- _ismbbkpunct
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ismbbkpunct_l
- _ismbbkpunct_l
- ismbbkpunct
- _ismbbkpunct
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkpunct_l function
- ismbbkpunct_l function
- ismbbkpunct function
- _ismbbkpunct function
ms.assetid: a04c59cd-5ca7-4296-bec0-2b0d7f04edd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e020957b418a2c6a61cda9a5c8c197fb149146d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400145"
---
# <a name="ismbbkpunct-ismbbkpunctl"></a>_ismbbkpunct, _ismbbkpunct_l

Verifica se um caractere multibyte é um caractere de pontuação.

## <a name="syntax"></a>Sintaxe

```C
int _ismbbkpunct(
   unsigned int c
);
int _ismbbkpunct_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parâmetros

*c*<br/>
Inteiro a ser testado.

*locale*<br/>
Localidade a usar.

## <a name="return-value"></a>Valor de retorno

**ismbbkpunct** retorna um valor diferente de zero se o número inteiro *c* é um símbolo de pontuação não-ASCII, ou 0 se não for. Por exemplo, somente na página de código 932, **_ismbbkpunct** testa se há pontuação katakana. **ismbbkpunct** usa a localidade atual para as configurações de caractere dependente de localidade. **ismbbkpunct_l** é idêntico, exceto que ele usa a localidade que é transmitida. Para obter mais informações, consulte [Localidade](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**_ismbbkpunct**|\<mbctype.h>|
|**_ismbbkpunct_l**|\<mbctype.h>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[Classificação de byte](../../c-runtime-library/byte-classification.md)<br/>
[Rotinas _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>
