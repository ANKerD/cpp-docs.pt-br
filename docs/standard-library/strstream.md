---
title: '&lt;strstream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <strstream>
dev_langs: C++
helpviewer_keywords: strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0487fc2aa09568523c6a7d0bbcf4973beee309ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;
Define várias classes que dão suporte a operações de iostreams em sequências armazenadas em uma matriz alocada do `char` objeto. Essas sequências facilmente são convertidas em cadeias de caracteres C.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
#include <strstream>  
  
```  
  
## <a name="remarks"></a>Comentários  
 Objetos do tipo `strstream` funcionam com `char` *, que são cadeias de caracteres C. Use [ \<sstream >](../standard-library/sstream.md) para trabalhar com objetos do tipo [basic_string](../standard-library/basic-string-class.md).  
  
> [!NOTE]
>  As classes em `<strstream>` são preteridas. Considere usar as classes em `<sstream>`, em vez disso.  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[Classe strstreambuf](../standard-library/strstreambuf-class.md)|A classe descreve um buffer de fluxo que controla a transmissão de elementos em uma sequência de elementos armazenados em um `char` objeto de matriz.|  
|[Classe istrstream](../standard-library/istrstream-class.md)|A classe descreve um objeto que controla a extração de elementos e objetos codificados de um buffer de fluxo da classe [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[Classe ostrstream](../standard-library/ostrstream-class.md)|A classe descreve um objeto que controla a inserção de elementos e objetos codificados de um buffer de fluxo da classe [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[Classe strstream](../standard-library/strstream-class.md)|A classe descreve um objeto que controla a inserção e extração de elementos e objetos codificados usando um buffer de fluxo da classe [strstreambuf](../standard-library/strstreambuf-class.md).|  
  
## <a name="see-also"></a>Consulte também  
 [\<strstream>](../standard-library/strstream.md)   
 [Referência de Arquivos de Cabeçalho](../standard-library/cpp-standard-library-header-files.md)   
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Programação de iostream](../standard-library/iostream-programming.md)   
 [Convenções de iostreams](../standard-library/iostreams-conventions.md)


