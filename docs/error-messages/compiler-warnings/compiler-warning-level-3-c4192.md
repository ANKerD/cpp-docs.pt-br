---
title: "Compilador aviso (nível 3) C4192 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4192
dev_langs: C++
helpviewer_keywords: C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 022c0e0aac8d231963ddf6d5d3715d55f726a8b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4192"></a>Compilador C4192 de aviso (nível 3)
excluindo automaticamente 'name' durante a importação de biblioteca de tipos 'library'  
  
 Um `#import` biblioteca contém um item, *nome*, que é também definido nos cabeçalhos de sistema do Win32. Devido às limitações das bibliotecas de tipo, nomes, como **IUnknown** ou GUID geralmente são definidas em uma biblioteca de tipos, duplicar a definição de cabeçalhos de sistema. `#import`detectará esses itens e recusar incorporá-las nos arquivos de cabeçalho. TLH e .tli.  
  
 Para substituir esse comportamento, use `#import` atributos [no_auto_exclude](../../preprocessor/no-auto-exclude.md) e [include()](../../preprocessor/include-parens.md).