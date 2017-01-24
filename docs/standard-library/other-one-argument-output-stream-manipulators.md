---
title: "Outros Manipuladores de Fluxo de Sa&#237;da de um Argumento | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fluxos de saída, manipuladores com um argumento"
ms.assetid: e381dee8-6b16-4cef-805a-4a6a1d2b696b
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Outros Manipuladores de Fluxo de Sa&#237;da de um Argumento
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

O exemplo a seguir usa uma classe `money`, que é um tipo de `long` .  O manipulador de `setpic` anexa uma cadeia de caracteres de “imagem” de formatação para a classe que pode ser usada pelo operador sobrecarregado de inserção do fluxo da classe `money`.  A cadeia de caracteres de imagem for armazenada como uma variável estático na classe de `money` em vez de como o membro de dados de uma classe de fluxo, de modo que não têm que deve derivar uma nova classe do fluxo de saída.  
  
## Exemplo  
  
```  
// one_arg_output.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
#include <string>  
using namespace std;  
  
typedef char* charp;  
  
class money   
{  
private:  
    long value;  
    static char *szCurrentPic;  
public:  
    money( long val ) { value = val; }  
    friend ostream& operator << ( ostream& os, money m ) {  
        // A more complete function would merge the picture  
        // with the value rather than simply appending it  
        os << m.value << '[' << money::szCurrentPic << ']';  
        return os;  
    }  
    static void setpic( char* szPic ) {  
        money::szCurrentPic = new char[strlen( szPic ) + 1];  
        strcpy_s( money::szCurrentPic, strlen( szPic ) + 1, szPic );  
    }  
};  
  
char *money::szCurrentPic;  // Static pointer to picture  
  
void fb( ios_base& os, char * somename )  
{  
   money::setpic(somename);  
/*  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
*/  
}  
  
_Smanip<charp>  
   __cdecl setpic(char * somename)  
   {     
   return (_Smanip<charp>(&fb, somename));  
   }  
  
int main( )  
{  
    money amt = (long)35235.22;  
    cout << setiosflags( ios::fixed );  
    cout << setpic( "###,###,###.##" ) << "amount = " << amt << endl;  
}  
```  
  
## Consulte também  
 [Manipuladores personalizados com argumentos](../standard-library/custom-manipulators-with-arguments.md)