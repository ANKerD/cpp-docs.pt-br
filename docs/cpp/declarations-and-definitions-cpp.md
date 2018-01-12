---
title: "Declarações e definições (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea0f8210993e494cbd4795a2c4cf7c6c0afa8aa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="declarations-and-definitions-c"></a>Declarações e definições (C++)
Declarações de introduzem nomes em um programa, por exemplo, os nomes de variáveis, namespaces, funções e classes. Declarações também especificam informações de tipo, bem como outras características do objeto que está sendo declarado. Um nome deve ser declarado antes que ele pode ser usado; em C++ o ponto no qual um nome é declarado determina se ele está visível para o compilador. Você não pode se referir a uma função ou uma classe que está declarada em algum momento posterior na unidade de compilação; Você pode usar *declarações de encaminhamento* para contornar essa limitação.  
  
 Definições de especificam quais códigos ou dados descreve o nome. O compilador precisa a definição para alocar espaço de armazenamento para o item que está sendo declarado.  
  
## <a name="declarations"></a>Declarações  
 Uma declaração introduz um ou mais nomes em um programa. As declarações podem ocorrer mais de uma vez em um programa. Portanto, é possível declarar classes, estruturas, tipos enumerados e outros tipos definidos pelo usuário para cada unidade de compilação. A restrição nessa declaração múltipla é que todas as declarações devem ser idênticas. As declarações também servem como definições, exceto quando a declaração:  
  
1.  É um protótipo de função (uma declaração de função sem o corpo da função).  
  
2.  Contém o especificador `extern`, mas não contém nenhum inicializador (objetos e variáveis) nem o corpo da função (funções). Isso significa que a definição não está necessariamente na unidade de tradução atual e atribui ao nome uma vinculação externa.  
  
3.  É de um membro de dados estático dentro de uma declaração de classe.  
  
     Como os membros de dados de classe estáticos são variáveis distintas compartilhadas por todos os objetos da classe, eles devem ser definidos e inicializados fora da declaração de classe. (Para obter mais informações sobre classes e membros de classe, consulte [Classes](../cpp/classes-and-structs-cpp.md).)  
  
4.  É uma declaração de nome de classe que não é seguida por uma definição, como `class T;`.  
  
5.  É uma instrução `typedef`.  
  
 Estes são exemplos de declarações que também são definições:  
  
```  
// Declare and define int variables i and j.  
int i;  
int j = 10;  
  
// Declare enumeration suits.  
enum suits { Spades = 1, Clubs, Hearts, Diamonds };  
  
// Declare class CheckBox.  
class CheckBox : public Control  
{  
public:  
            Boolean IsChecked();  
    virtual int     ChangeState() = 0;  
};  
```  
  
 Estas são algumas declarações que não são definições:  
  
```  
  
extern int i;  
char *strchr( const char *Str, const char Target );  
```  
  
 Um nome é considerado declarado imediatamente após seu declarator, mas antes de seu inicializador (opcional). Para obter mais informações, consulte [ponto de declaração](../cpp/point-of-declaration-in-cpp.md).  
  
 Declarações ocorrem em um *escopo*. O escopo controla a visibilidade do nome declarado e a duração do objeto definido, se houver. Para obter mais informações sobre como as regras de escopo interagem com declarações, consulte [escopo](../cpp/scope-visual-cpp.md).  
  
 Uma declaração de objeto também é uma definição, a menos que ele contenha o `extern` especificador de classe de armazenamento descrito em [classes de armazenamento](storage-classes-cpp.md). Uma declaração de função também é uma definição a menos que seja um protótipo. Um protótipo é um cabeçalho da função sem um corpo da definição da função. A definição de um objeto resulta na alocação de armazenamento e inicializações apropriadas para esse objeto.  
  
## <a name="definitions"></a>Definições  
 Uma definição é uma especificação exclusiva de um objeto ou variável, função, classe ou enumerador. Como as definições devem ser exclusivas, um programa só pode conter uma definição para um dado elemento do programa. Pode haver uma correspondência muitos para um entre declarações e definições. Há dois casos em que um elemento do programa pode ser declarado e não definido:  
  
1.  Uma função é declarada mas nunca referenciada com uma chamada de função ou com uma expressão que usa o endereço da função.  
  
2.  Uma classe é usada somente de um modo que não exige que sua definição seja conhecida. No entanto, a classe deve ser declarada. O código a seguir ilustra esse caso:  
  
    ```  
    // definitions.cpp  
    class WindowCounter;   // Forward declaration; no definition  
  
    class Window  
    {  
       // Definition of WindowCounter not required  
       static WindowCounter windowCounter;  
    };  
  
    int main()  
    {  
    }  
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Conceitos básicos](../cpp/basic-concepts-cpp.md)   
 [Ponto de declaração](../cpp/point-of-declaration-in-cpp.md)