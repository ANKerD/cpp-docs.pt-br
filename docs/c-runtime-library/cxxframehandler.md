---
title: "__CxxFrameHandler | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__CxxFrameHandler"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__CxxFrameHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__CxxFrameHandler"
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __CxxFrameHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Função CRT interna.  Usada pelo CRT para identificar quadros estruturados de exceção.  
  
## Sintaxe  
  
```cpp  
EXCEPTION_DISPOSITION __CxxFrameHandler(       EHExceptionRecord  *pExcept,       EHRegistrationNode *pRN,       void               *pContext,        DispatcherContext  *pDC    )  
```  
  
#### Parâmetros  
 `pExcept`  
 Registro de exceção passado para as instruções `catch` possíveis.  
  
 `pRN`  
 Informações dinâmicas sobre o registro de ativação usado para identificar a exceção.  Para obter mais informações, consulte ehdata.h.  
  
 `pContext`  
 Contexto.  \(Não usado em processadores da Intel.\)  
  
 `pDC`  
 Informações adicionais sobre a entrada da função e o registro de ativação.  
  
## Valor de retorno  
 Um dos valores da *expressão de filtro* usados pelo [Instrução try\-except](../cpp/try-except-statement.md).  
  
## Comentários  
  
## Requisitos  
  
|Rotina|Cabeçalho necessário|  
|------------|--------------------------|  
|\_\_CxxFrameHandler|excpt.h, ehdata.h|