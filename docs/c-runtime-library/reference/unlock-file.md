---
title: _unlock_file | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _unlock_file
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _unlock_file
- unlock_file
dev_langs:
- C++
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63b0950aaea5520849f9a32b2b08ab138cd8099b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107514"
---
# <a name="unlockfile"></a>_unlock_file

Desbloqueia um arquivo, permitindo que outros processos acessem o arquivo.

## <a name="syntax"></a>Sintaxe

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>Parâmetros

*file*<br/>
Identificador de arquivo.

## <a name="remarks"></a>Comentários

O **unlock_file** função desbloqueia o arquivo especificado por *arquivo*. Desbloquear um arquivo permite o acesso ao arquivo por outros processos. Essa função não deve ser chamada, a menos que **lock_file** foi chamado anteriormente sobre o *arquivo* ponteiro. Chamando **unlock_file** em um arquivo que não esteja bloqueado pode resultar em um deadlock. Para um exemplo, consulte [_lock_file](lock-file.md).

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[Manipulação de Arquivos](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
