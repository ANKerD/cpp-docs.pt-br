---
title: operador&gt;= (stack) (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::operator>=
dev_langs:
- C++
helpviewer_keywords:
- operator>= member [STL/CLR]
ms.assetid: d0c757fa-9d40-40c7-89f7-baf30b22d899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d59fad17a7f10f0bc8b078ee80ebe9a118a2d4fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
---
# <a name="operatorgt-stack-stlclr"></a>operador&gt;= (stack) (STL/CLR)
Pilha maior que ou igual a comparação.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template<typename Value,  
    typename Container>  
    bool operator>=(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 esquerda  
 Contêiner esquerdo a comparar.  
  
 direita  
 Contêiner direito a comparar.  
  
## <a name="remarks"></a>Comentários  
 Retorna a função de operador `!(left < right)`. Você pode usá-lo para testar se `left` não for ordenado antes `right` quando duas pilhas são comparado elemento pelo elemento.  
  
## <a name="example"></a>Exemplo  
  
```  
// cliext_stack_operator_ge.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] >= [a b c] is True  
[a b c] >= [a b d] is False  
```  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<cliext/pilha >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Consulte também  
 [pilha (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [operador = = (stack) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)   
 [operador! = (stack) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [operador\< (stack) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)   
 [operador > (stack) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)