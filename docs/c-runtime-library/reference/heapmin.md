---
title: _heapmin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _heapmin
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _heapmin
- heapmin
dev_langs:
- C++
helpviewer_keywords:
- heap memory
- minimizing heaps
- memory, releasing
- heaps, releasing unused memory
- _heapmin function
- heapmin function
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec73905c6361d025b9f29c8cf4543ed200a4abbf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397977"
---
# <a name="heapmin"></a>_heapmin

Libera memória de heap não utilizada para o sistema operacional.

## <a name="syntax"></a>Sintaxe

```C
int _heapmin( void );
```

## <a name="return-value"></a>Valor de retorno

Se for bem-sucedido, **heapmin** retorna 0; caso contrário, a função retornará -1 e define **errno** para **ENOSYS**.

Para obter mais informações sobre este e outros códigos retornados, consulte [_doserrno, errno, _sys_errlist e _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Comentários

O **heapmin** função minimiza o heap, liberando memória heap não utilizados para o sistema operacional. Se o sistema operacional não suporta **heapmin**(por exemplo, Windows 98), a função retornará -1 e define **errno** para **ENOSYS**.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|Cabeçalho opcional|
|-------------|---------------------|---------------------|
|**_heapmin**|\<malloc.h>|\<errno.h>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[Alocação de Memória](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
[malloc](malloc.md)<br/>
