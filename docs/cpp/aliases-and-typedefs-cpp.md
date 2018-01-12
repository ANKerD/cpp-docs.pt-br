---
title: Aliases e typedefs (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: typedef_cpp
dev_langs: C++
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8946c87c18e1781f95df7a91e8cc4fa0eba02158
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="aliases-and-typedefs-c"></a>Aliases e typedefs (C++)
Você pode usar um *declaração de alias* para declarar um nome a ser usado como um sinônimo para um tipo declarado anteriormente. (Esse mecanismo também é chamado informalmente como um *alias de tipo*). Você também pode usar esse mecanismo para criar um *modelo de alias*, que pode ser particularmente útil para alocadores personalizados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
using identifier = type;  
```  
  
## <a name="remarks"></a>Comentários  
 `identifier`  
 O nome do alias.  
  
 `type`  
 O identificador de tipo para o qual você está criando um alias.  
  
 Um alias não introduz um novo tipo e não podem alterar o significado de um nome de tipo existente.  
  
 A forma mais simples de alias é equivalente ao mecanismo `typedef` de C++03:  
  
```cpp  
// C++11  
using counter = long;  
  
// C++03 equivalent:  
// typedef long counter;  
```  
  
 Os dois permitem a criação de variáveis do tipo “counter”. Algo mais útil seria um alias de tipo para `std::ios_base::fmtflags` como este:  
  
```cpp  
// C++11  
using fmtfl = std::ios_base::fmtflags;  
  
// C++03 equivalent:  
// typedef std::ios_base::fmtflags fmtfl;  
  
fmtfl fl_orig = std::cout.flags();  
fmtfl fl_hex = (fl_orig & ~std::cout.basefield) | std::cout.showbase | std::cout.hex;  
// ...  
std::cout.flags(fl_hex);  
```  
  
 Aliases também funcionam com ponteiros de função, mas são muito mais legíveis que typedef equivalente:  
  
```cpp  
// C++11  
using func = void(*)(int);  
  
// C++03 equivalent:  
// typedef void (*func)(int);  
  
// func can be assigned to a function pointer value  
void actual_function(int arg) { /* some code */ }  
func fptr = &actual_function;  
  
```  
  
 Uma restrição do mecanismo `typedef` é que ele não funciona com modelos. No entanto, a sintaxe de alias de tipo no C++11 permite a criação de modelos de alias:  
  
```cpp  
template<typename T> using ptr = T*;   
  
// the name 'ptr<T>' is now an alias for pointer to T  
ptr<int> ptr_int;  
  
```  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir demonstra como usar um modelo de alias com um alocador personalizado – nesse caso, um tipo de vetor de inteiro. Você pode substituir qualquer tipo por `int` para criar um alias conveniente para ocultar as listas de parâmetros complexas em seu código funcional principal. Ao usar o alocador personalizado em todo o seu código, você pode melhorar a legibilidade e reduzir o risco de introduzir bugs causados por erros de digitação.  
  
```cpp  
#include <stdlib.h>  
#include <new>  
  
template <typename T> struct MyAlloc {  
    typedef T value_type;  
  
    MyAlloc() { }  
    template <typename U> MyAlloc(const MyAlloc<U>&) { }  
  
    bool operator==(const MyAlloc&) const { return true; }  
    bool operator!=(const MyAlloc&) const { return false; }  
  
    T * allocate(const size_t n) const {  
        if (n == 0) {  
            return nullptr;  
        }  
  
        if (n > static_cast<size_t>(-1) / sizeof(T)) {  
            throw std::bad_array_new_length();  
        }  
  
        void * const pv = malloc(n * sizeof(T));  
  
        if (!pv) {  
            throw std::bad_alloc();  
        }  
  
        return static_cast<T *>(pv);  
    }  
  
    void deallocate(T * const p, size_t) const {  
        free(p);  
    }  
};  
  
#include <vector>  
using MyIntVector = std::vector<int, MyAlloc<int>>;  
  
#include <iostream>  
  
int main ()   
{  
    MyIntVector foov = { 1701, 1764, 1664 };  
  
    for (auto a: foov) std::cout << a << " ";  
    std::cout << "\n";  
  
    return 0;  
}  
```  
  
```Output  
1701 1764 1664  
```  
  
## <a name="typedefs"></a>Typedefs  
 Um `typedef` declaração apresenta um nome que, dentro de seu escopo, se torna um sinônimo para o tipo de dado pelo *declaração de tipo* parte da declaração.  
  
 Você pode usar declarações de typedef para construir nomes mais curtos ou mais significativos para os tipos já definidos pelo idioma ou para os tipos que você declarou. Os nomes de typedef permitem que você encapsule os detalhes da implementação que podem ser alterados.  
  
 Em comparação com o **classe**, `struct`, **união**, e `enum` declarações, `typedef` declarações não apresenta novos tipos — introduzem novos nomes para os tipos existentes.  
  
 Nomes declarados usando `typedef` ocupam o mesmo namespace que outros identificadores (exceto rótulos de instrução). Portanto, não podem usar o mesmo identificador de um nome declarado anteriormente, exceto em uma declaração de tipo de classe. Considere o exemplo a seguir:  
  
```  
// typedef_names1.cpp  
// C2377 expected  
typedef unsigned long UL;   // Declare a typedef name, UL.  
int UL;                     // C2377: redefined.  
```  
  
 As regras de ocultação de nome pertencentes a outros identificadores também controlam a visibilidade dos nomes declarados usando `typedef`. Portanto, o exemplo a seguir é válido em C++:  
  
```  
// typedef_names2.cpp  
typedef unsigned long UL;   // Declare a typedef name, UL  
int main()  
{  
   unsigned int UL;   // Redeclaration hides typedef name  
}  
  
// typedef UL back in scope  
```  
 
  
```  
// typedef_specifier1.cpp  
typedef char FlagType;  
  
int main()  
{  
}  
  
void myproc( int )  
{  
    int FlagType;  
}  
```  
  
 Ao declarar um identificador de escopo local com o mesmo nome de um typedef, ou ao declarar um membro de uma estrutura ou de uma união no mesmo escopo ou em um escopo interno, o especificador do tipo deverá ser especificado. Por exemplo:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Para reutilizar o nome `FlagType` para um identificador, um membro da estrutura ou da união, o tipo deve ser fornecido:  
  
```  
const int FlagType;  // Type specifier required  
```  
  
 Não é suficiente indicar  
  
```  
const FlagType;      // Incomplete specification  
```  
  
 pois `FlagType` é tomado como parte do tipo, não como um identificador que redeclarado. Esta declaração é executada para ser uma declaração inválida como  
  
```  
int;  // Illegal declaration   
```  
  
 Você pode declarar qualquer tipo com typedef, incluindo o ponteiro, função e tipos de matriz. Você pode declarar um nome de typedef para um ponteiro para um tipo de estrutura ou união antes de definir o tipo da estrutura ou de união, contanto que a definição tenha a mesma visibilidade da declaração.  
  
### <a name="examples"></a>Exemplos  
 Um uso de declarações `typedef` é tornar as declarações mais uniformes e compactas. Por exemplo:  
  
```cpp  
typedef char CHAR;          // Character type.  
typedef CHAR * PSTR;        // Pointer to a string (char *).  
PSTR strchr( PSTR source, CHAR target );  
typedef unsigned long ulong;  
ulong ul;     // Equivalent to "unsigned long ul;"  
```  
  
 Para usar `typedef` para especificar tipos fundamentais e derivados na mesma declaração, você pode separar os declaradores com vírgulas. Por exemplo:  
  
```  
typedef char CHAR, *PSTR;  
```  
  
 O exemplo a seguir fornece o tipo `DRAWF` para uma função que não retorna valor e que usa dois argumentos int:  
  
```  
typedef void DRAWF( int, int );  
```  
  
 Após a instrução de `typedef` anterior, a declaração  
  
```  
DRAWF box;   
```  
  
 é equivalente à declaração  
  
```  
void box( int, int );  
```  
  
 `typedef` é combinado com frequência com `struct` para declarar e nomear tipos definidos pelo usuário:  
  
```cpp  
// typedef_specifier2.cpp  
#include <stdio.h>  
  
typedef struct mystructtag  
{  
    int   i;  
    double f;  
} mystruct;  
  
int main()  
{  
    mystruct ms;  
    ms.i = 10;  
    ms.f = 0.99;  
    printf_s("%d   %f\n", ms.i, ms.f);  
}  
```  
  
```Output  
10   0.990000  
```  
  
### <a name="re-declaration-of-typedefs"></a>Nova declaração de typedefs  
 A declaração `typedef` pode ser usada para redeclarar o mesmo nome para fazer referência ao mesmo tipo. Por exemplo:  
  
```cpp  
// FILE1.H  
typedef char CHAR;  
  
// FILE2.H  
typedef char CHAR;  
  
// PROG.CPP  
#include "file1.h"  
#include "file2.h"   // OK  
```  
  
 O programa PROG.CPP inclui dois arquivos de cabeçalho, os quais contêm declarações `typedef` para o nome `CHAR`. Contanto que as duas declarações façam referência ao mesmo tipo, essa redeclaração é aceitável.  
  
 Um `typedef` não pode redefinir um nome que foi declarado anteriormente como um tipo diferente. Portanto, se FILE2.H contém  
  
```cpp  
// FILE2.H  
typedef int CHAR;     // Error  
```  
  
 o compilador emite um erro devido à tentativa de redeclarar o nome `CHAR` para fazer referência a um tipo diferente. Isso se estende a construtos como:  
  
```cpp  
typedef char CHAR;  
typedef CHAR CHAR;      // OK: redeclared as same type  
  
typedef union REGS      // OK: name REGS redeclared  
{                       //  by typedef name with the  
    struct wordregs x;  //  same meaning.  
    struct byteregs h;  
} REGS;  
```  
  
### <a name="typedefs-in-c-vs-c"></a>definições de tipo em C++ vs. C  
 O uso do especificador `typedef` com tipos de classe tem amplo suporte devido à prática de ANSI C de declaração de estruturas sem nome em declarações `typedef`. Por exemplo, muitos desenvolvedores de C usam o seguinte:  
  
```cpp  
// typedef_with_class_types1.cpp  
// compile with: /c  
typedef struct {   // Declare an unnamed structure and give it the  
                   // typedef name POINT.  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 A vantagem dessa declaração é que ela permite declarações como:  
  
```  
POINT ptOrigin;  
```  
  
 em vez de:  
  
```  
struct point_t ptOrigin;  
```  
  
 No C++, a diferença entre `typedef` nomes e tipos reais (declarado com o **classe**, `struct`, **união**, e `enum` palavras-chave) é mais diferente. Embora a prática de C de declarar uma estrutura sem nome em uma instrução `typedef` ainda funcione, ela não fornece nenhum benefício notacional como em C.  
  
```cpp  
// typedef_with_class_types2.cpp  
// compile with: /c /W1  
typedef struct {  
   int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 O exemplo anterior declara uma classe chamada `POINT` usando a sintaxe `typedef` da classe sem nome. `POINT` é tratado como um nome de classe; no entanto, as seguintes restrições se aplicam aos nomes introduzidos desta forma:  
  
-   O nome (o sinônimo) não pode aparecer após uma **classe**, `struct`, ou **união** prefixo.  
  
-   O nome não pode ser usado como nomes de construtor ou destruidor dentro de uma declaração da classe.  
  
 Em resumo, essa sintaxe não fornece um mecanismo para herança, construção ou destruição.  