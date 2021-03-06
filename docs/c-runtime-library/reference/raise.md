---
title: raise | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- raise
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- Raise
dev_langs:
- C++
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1bc3f52b97159a9caba6f80b4798d9588ec341d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685902"
---
# <a name="raise"></a>raise

Envia um sinal para o programa em execução.

> [!NOTE]
> Não use esse método para desligar um aplicativo da Microsoft Store, exceto em teste ou cenários de depuração. Maneiras programáticas ou interface do usuário de fechar um aplicativo da Store não são permitidas de acordo com o [políticas do Microsoft Store](/legal/windows/agreements/store-policies). Para obter mais informações, consulte [ciclo de vida do aplicativo UWP](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sintaxe

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Parâmetros

*sig*<br/>
Sinal a ser gerado.

## <a name="return-value"></a>Valor de retorno

Se for bem-sucedido, **raise** retornará 0. Caso contrário, retornará um valor diferente de zero.

## <a name="remarks"></a>Comentários

A função **raise** envia *sig* para o programa em execução. Se uma chamada anterior a **signal** tiver instalado uma função de manipulação de sinal para *sig*, **raise** executará essa função. Se nenhuma função de manipulador tiver sido instalada, a ação padrão associada com o valor de sinal *sig* será obtida da seguinte maneira.

|Sinal|Significado|Padrão|
|------------|-------------|-------------|
|**SIGABRT**|Encerramento anormal|Termina o programa de chamada com código de saída 3|
|**SIGFPE**|Erro de ponto flutuante|Encerra o programa de chamada|
|**SIGILL**|Instrução ilegal|Encerra o programa de chamada|
|**SIGINT**|Interrupção CTRL+C|Encerra o programa de chamada|
|**SIGSEGV**|Acesso ao armazenamento inválido|Encerra o programa de chamada|
|**SIGTERM**|Solicitação de término enviado para o programa|Ignora o sinal|

Se o argumento não for um sinal válido conforme especificado acima, o manipulador de parâmetro inválido é invocado, conforme descrito em [Validação de parâmetro](../../c-runtime-library/parameter-validation.md). Se não tratada, a função definirá **errno** à **EINVAL** e retorna um valor diferente de zero.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|
|-------------|---------------------|
|**raise**|\<signal.h>|

Para obter informações adicionais sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Consulte também

[Controle de processo e de ambiente](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[signal](signal.md)<br/>
