---
title: _getdiskfree | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _getdiskfree
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
- getdiskfree
- _getdiskfree
dev_langs: C++
helpviewer_keywords:
- diskfree_t type
- _getdiskfree function
- _diskfree_t type
- disk size
- getdiskfree function
ms.assetid: 47a3f6cf-4816-452a-8f3d-1c3ae02a0f2a
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3adc229f9e3ea174b29f6bbcadb05bc3be30fc6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="getdiskfree"></a>_getdiskfree
Usa informações sobre uma unidade de disco para popular uma estrutura `_diskfree_t`.  
  
> [!IMPORTANT]
>  Esta API não pode ser usada em aplicativos executados no Tempo de Execução do Windows. Para obter mais informações, consulte [Funções de CRT sem suporte com /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
unsigned _getdiskfree(  
   unsigned drive,  
   struct _diskfree_t * driveinfo  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 [in] `drive`  
 A unidade de disco cujas informações você deseja.  
  
 [out] `driveinfo`  
 Uma estrutura `_diskfree_t` que será populada com informações sobre a unidade.  
  
## <a name="return-value"></a>Valor de retorno  
 Se a função obtiver êxito, o valor retornado será zero. Se a função falhar, o valor retornado será o código de erro. O valor `errno` está definido para os erros retornados pelo sistema operacional. Para obter mais informações sobre as condições de erro indicadas por `errno`, consulte [Constantes errno](../../c-runtime-library/errno-constants.md).  
  
## <a name="remarks"></a>Comentários  
 A estrutura `_diskfree_t` é definida em Direct.h.  
  
```  
struct _diskfree_t {   
   unsigned total_clusters;   
   unsigned avail_clusters;   
   unsigned sectors_per_cluster;   
   unsigned bytes_per_sector;   
};  
```  
  
 Essa função valida seus parâmetros. Se o ponteiro `driveinfo` for `NULL` ou `drive` especificar uma unidade inválida, a função invocará o manipulador de parâmetro inválido, conforme descrito em [Validação de parâmetro](../../c-runtime-library/parameter-validation.md). Se a execução puder continuar, a função retornará `EINVAL` e definirá `errno` como `EINVAL`. Intervalo de unidades válidas, de 0 a 26. Um valor de `drive` igual a 0 especifica a unidade atual; depois disso, os números são mapeados para letras do alfabeto inglês, de forma que 1 indica a unidade A, 3 indica a unidade C e assim por diante.  
  
 `total_clusters`  
 O número total de clusters, usados e disponíveis, no disco.  
  
 `avail_clusters`  
 O número de clusters não utilizados no disco.  
  
 `sectors_per_cluster`  
 O número de setores em cada cluster.  
  
 `bytes_per_sector`  
 O tamanho de cada setor em bytes.  
  
## <a name="requirements"></a>Requisitos  
  
|Rotina|Cabeçalho necessário|  
|-------------|---------------------|  
|`_getdiskfree`|\<direct.h>|  
  
 Para obter mais informações sobre compatibilidade, consulte [Compatibilidade](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemplo  
  
```C  
// crt_getdiskfree.c  
// compile with: /c  
#include <windows.h>  
#include <direct.h>  
#include <stdio.h>  
#include <tchar.h>  
  
TCHAR   g_szBorder[] = _T("======================================================================\n");  
TCHAR   g_szTitle1[] = _T("|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|\n");  
TCHAR   g_szTitle2[] = _T("|=====|==============|==============|=================|==============|\n");  
TCHAR   g_szLine[]   = _T("|  A: |              |              |                 |              |\n");  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal);  
  
int main(int argc, char* argv[]) {  
   TCHAR szMsg[4200];  
   struct _diskfree_t df = {0};  
   ULONG uDriveMask = _getdrives();  
   unsigned uErr, uLen, uDrive;  
  
   printf(g_szBorder);  
   printf(g_szTitle1);  
   printf(g_szTitle2);  
  
   for (uDrive=1; uDrive<=26; ++uDrive) {  
      if (uDriveMask & 1) {  
         uErr = _getdiskfree(uDrive, &df);  
         memcpy(szMsg, g_szLine, sizeof(g_szLine));  
         szMsg[3] = uDrive + 'A' - 1;  
  
         if (uErr == 0) {  
            utoiRightJustified(szMsg+8,  szMsg+19, df.total_clusters);  
            utoiRightJustified(szMsg+23, szMsg+34, df.avail_clusters);  
            utoiRightJustified(szMsg+38, szMsg+52, df.sectors_per_cluster);  
            utoiRightJustified(szMsg+56, szMsg+67, df.bytes_per_sector);  
         }  
         else {  
            uLen = FormatMessage(FORMAT_MESSAGE_FROM_SYSTEM, NULL,  
                            uErr, 0, szMsg+8, 4100, NULL);  
            szMsg[uLen+6] = ' ';  
            szMsg[uLen+7] = ' ';  
            szMsg[uLen+8] = ' ';  
         }  
  
         printf(szMsg);  
      }  
  
      uDriveMask >>= 1;  
   }  
  
   printf(g_szBorder);  
}  
  
void utoiRightJustified(TCHAR* szLeft, TCHAR* szRight, unsigned uVal) {  
   TCHAR* szCur = szRight;  
   int nComma = 0;  
  
   if (uVal) {  
      while (uVal && (szCur >= szLeft)) {  
         if   (nComma == 3) {  
            *szCur = ',';  
            nComma = 0;  
         }  
         else {  
            *szCur = (uVal % 10) | 0x30;  
            uVal /= 10;  
            ++nComma;  
         }  
  
         --szCur;  
      }  
   }  
   else {  
      *szCur = '0';  
      --szCur;  
   }  
  
   if (uVal) {  
      szCur = szLeft;  
  
      while   (szCur <= szRight) {  
         *szCur = '*';  
         ++szCur;  
      }  
   }  
}  
```  
  
```Output  
======================================================================  
|DRIVE|TOTAL CLUSTERS|AVAIL CLUSTERS|SECTORS / CLUSTER|BYTES / SECTOR|  
|=====|==============|==============|=================|==============|  
|  A: | The device is not ready.    |                 |              |  
|  C: |    4,721,093 |    3,778,303 |               8 |          512 |  
|  D: |    1,956,097 |    1,800,761 |               8 |          512 |  
|  E: | The device is not ready.    |                 |              |  
======================================================================  
```  
  
## <a name="see-also"></a>Consulte também  
 [Controle de diretório](../../c-runtime-library/directory-control.md)