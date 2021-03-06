---
title: _heapwalk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _heapwalk
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
- heapwalk
- _heapwalk
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d98260ce281bc8773f597dae5897afe4beee0bc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403395"
---
# <a name="heapwalk"></a>_heapwalk

Percorre o heap e retorna informações sobre a próxima entrada.

> [!IMPORTANT]
> Esta API não pode ser usada em aplicativos executados no Windows Runtime, exceto em builds de depuração. Para obter mais informações, confira [Funções do CRT sem suporte em aplicativos da Plataforma Universal do Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sintaxe

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>Parâmetros

*entryinfo*<br/>
Buffer que conterá informações do heap.

## <a name="return-value"></a>Valor de retorno

**heapwalk** retorna uma das seguintes constantes de manifesto de inteiro definidas em Malloc.h.

|Valor retornado|Significado|
|-|-|
|**HEAPBADBEGIN**| As informações do cabeçalho inicial são inválidas ou não foram encontradas.|
|**HEAPBADNODE**| Heap danificado ou nó inválido encontrado.|
|**HEAPBADPTR**| O **_pentry** campo o **heapinfo** estrutura não contém um ponteiro válido para o heap ou *entryinfo* é um ponteiro nulo.|
|**HEAPEND**| Fim do heap alcançado com êxito.|
|**HEAPEMPTY**| Heap não inicializado.|
|**HEAPOK**| Nenhum erro até certo ponto. *entryinfo* é atualizado com informações sobre a próxima entrada do heap.|

Além disso, se ocorrer um erro, **heapwalk** define **errno** para **ENOSYS**.

## <a name="remarks"></a>Comentários

O **heapwalk** função ajuda a depurar problemas relacionados a heap em programas. A função percorre o heap, percorrendo uma entrada por chamada e retorna um ponteiro para uma estrutura de tipo **heapinfo** que contém informações sobre a próxima entrada do heap. O **heapinfo** tipo definido em Malloc.h, contém os seguintes elementos.

|Campo|Significado|
|-|-|
|`int *_pentry`|Ponto de entrada do heap.|
|`size_t _size`|Tamanho da entrada do heap.|
|`int _useflag`|Sinalizador que indica se a entrada do heap está sendo utilizada.|

Uma chamada para **heapwalk** que retorna **heapok** armazena o tamanho da entrada no **_size** campo e conjuntos de **_useflag** campo como **Freeentry** ou **usedentry** (ambos são constantes definidas na Malloc.h). Para obter essas informações sobre a primeira entrada na pilha, passar **heapwalk** um ponteiro para um **heapinfo** estrutura cujo **_pentry** membro é **nulo** . Se o sistema operacional não suporta **heapwalk**(por exemplo, Windows 98), a função retorna **heapend** e define **errno** para **ENOSYS**.

Esta função valida seu parâmetro. Se *entryinfo* é um ponteiro nulo, o manipulador de parâmetro inválido é invocado, conforme descrito em [validação do parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução é permitida para continuar, **errno** é definido como **EINVAL** e a função retorna **heapbadptr**.

## <a name="requirements"></a>Requisitos

|Rotina|Cabeçalho necessário|Cabeçalho opcional|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc.h>|\<errno.h>|

Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Exemplo

```C
// crt_heapwalk.c

// This program "walks" the heap, starting
// at the beginning (_pentry = NULL). It prints out each
// heap entry's use, location, and size. It also prints
// out information about the overall state of the heap as
// soon as _heapwalk returns a value other than _HEAPOK
// or if the loop has iterated 100 times.

#include <stdio.h>
#include <malloc.h>

void heapdump(void);

int main(void)
{
    char *buffer;

    heapdump();
    if((buffer = (char *)malloc(59)) != NULL)
    {
        heapdump();
        free(buffer);
    }
    heapdump();
}

void heapdump(void)
{
    _HEAPINFO hinfo;
    int heapstatus;
    int numLoops;
    hinfo._pentry = NULL;
    numLoops = 0;
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&
          numLoops < 100)
    {
        printf("%8s block at %Fp of size %4.4X\n",
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),
               hinfo._pentry, hinfo._size);
        numLoops++;
    }

    switch(heapstatus)
    {
    case _HEAPEMPTY:
        printf("OK - empty heap\n");
        break;
    case _HEAPEND:
        printf("OK - end of heap\n");
        break;
    case _HEAPBADPTR:
        printf("ERROR - bad pointer to heap\n");
        break;
    case _HEAPBADBEGIN:
        printf("ERROR - bad start of heap\n");
        break;
    case _HEAPBADNODE:
        printf("ERROR - bad node in heap\n");
        break;
    }
}
```

```Output
    USED block at 00310650 of size 0100
    USED block at 00310758 of size 0800
    USED block at 00310F60 of size 0080
    FREE block at 00310FF0 of size 0398
    USED block at 00311390 of size 000D
    USED block at 003113A8 of size 00B4
    USED block at 00311468 of size 0034
    USED block at 003114A8 of size 0039
...
    USED block at 00312228 of size 0010
    USED block at 00312240 of size 1000
    FREE block at 00313250 of size 1DB0
OK - end of heap
```

## <a name="see-also"></a>Consulte também

[Alocação de Memória](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
