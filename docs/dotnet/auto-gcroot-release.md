---
title: "auto_gcroot::release | Microsoft Docs"
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
  - "msclr::auto_gcroot::release"
  - "auto_gcroot::release"
  - "auto_gcroot.release"
  - "msclr.auto_gcroot.release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "método de liberação"
ms.assetid: 40b253f0-154e-4d79-80a4-ff13199c3ff0
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::release
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libera o objeto de gerenciamento de `auto_gcroot` .  
  
## Sintaxe  
  
```  
_element_type release();  
```  
  
## Valor de retorno  
 O objeto liberado.  
  
## Exemplo  
  
```  
// msl_auto_gcroot_release.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );     
   }  
};  
  
int main()  
{  
   ClassA^ a;  
  
   // create a new scope:  
   {  
      auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );  
      auto_gcroot<ClassA^> agc2 = gcnew ClassA( "second" );  
      a = agc1.release();  
   }  
   // agc1 and agc2 go out of scope here  
  
   a->PrintHello();  
  
   Console::WriteLine( "done" );  
}  
```  
  
  **O construtor de ClassA: primeiro**  
**O construtor de ClassA: segundo**  
**Destruidor de ClassA: segundo**  
**Hello world primeiro de\!**  
**feita**   
## Requisitos  
 msclr \<de**Arquivo de cabeçalho** \\ auto\_gcroot.h\>  
  
 msclr de**Namespace**  
  
## Consulte também  
 [Membros auto\_gcroot](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::~auto\_gcroot](../Topic/auto_gcroot::~auto_gcroot.md)