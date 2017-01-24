---
title: "C3415 de erro do compilador | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3415"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3415"
ms.assetid: fa2db8ab-2820-4ec3-a740-fb5e2adcfb29
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C3415 de erro do compilador
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

várias seções de 'section\_name' encontradas com diferentes atributos \('value'\)  
  
 Valores conflitantes foram especificados na [seção](../../preprocessor/section.md) pragmas.  
  
 `value` é a configuração atual para a seção, conforme especificado em ntimage.h. Por exemplo:  
  
```  
// Section contains extended relocations. #define IMAGE_SCN_LNK_NRELOC_OVFL            0x01000000 // Section can be discarded. #define IMAGE_SCN_MEM_DISCARDABLE            0x02000000 // Section is not cachable. #define IMAGE_SCN_MEM_NOT_CACHED             0x04000000 // Section is not pageable. #define IMAGE_SCN_MEM_NOT_PAGED              0x08000000 // Section is shareable. #define IMAGE_SCN_MEM_SHARED                 0x10000000 // Section is executable. #define IMAGE_SCN_MEM_EXECUTE                0x20000000 // Section is readable. #define IMAGE_SCN_MEM_READ                   0x40000000 // Section is writeable. #define IMAGE_SCN_MEM_WRITE                  0x80000000    
```  
  
 O exemplo a seguir gera C3415:  
  
```  
// C3415.cpp #pragma section("mysec1",write) #pragma section("mysec1",read)   // C3415  
```