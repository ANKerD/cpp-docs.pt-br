---
title: "hash_set::begin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iniciar membro [STL/CLR]"
ms.assetid: 1bd02b6b-0e24-4f42-ad13-fd7776f7f811
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::begin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Designa o início da sequência controlada.  
  
## Sintaxe  
  
```  
iterator begin();  
```  
  
## Comentários  
 A função de membro retorna um iterador bidirecional que designa o primeiro elemento da sequência controlada, ou apenas além do de uma sequência vazia.  Use\-a para obter um iterador que designa o início de `current` de sequência controlada, mas seu status pode ser alterado se o comprimento da sequência controlada é alterado.  
  
## Exemplo  
  
```  
// cliext_hash_set_begin.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Myhash_set::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
  **um b c**  
**\*begin\(\) \= a**  
**\*\+\+begin\(\) \= b**   
## Requisitos  
 cliext \<\/hash\_set de**Cabeçalho:** \>  
  
 cliext de**Namespace:**  
  
## Consulte também  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)