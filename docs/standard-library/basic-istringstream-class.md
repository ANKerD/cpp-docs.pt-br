---
title: Classe basic_istringstream | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
dev_langs: C++
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc439bd64327ad48f98de8eef380a792e54b8c4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="basicistringstream-class"></a>Classe basic_istringstream
Descreve um objeto que controla a extração de elementos e objetos codificados de um buffer de fluxo da classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `Alloc`  
 A classe do alocador.  
  
 `Elem`  
 O tipo do elemento básico da cadeia de caracteres.  
  
 *Tr*  
 As características de caractere especializadas no elemento básico da cadeia de caracteres.  
  
## <a name="remarks"></a>Comentários  
 A classe de modelo descreve um objeto que controla a extração de elementos e objetos codificados de um buffer de fluxo da classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, com elementos do tipo **Elem**, cujas características de caractere são determinadas pela classe **Tr** e cujos elementos são alocados por um alocador de classe `Alloc`. O objeto armazena um objeto da classe basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Construtores  
  
|||  
|-|-|  
|[basic_istringstream](#basic_istringstream)|Constrói um objeto do tipo `basic_istringstream`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|O tipo é um sinônimo do parâmetro de modelo `Alloc`.|  
  
### <a name="member-functions"></a>Funções membro  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Retorna o endereço do buffer de fluxo armazenado do tipo `pointer` para [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|  
|[str](#str)|Define ou obtém o texto em um buffer de cadeia de caracteres sem alterar a posição de gravação.|  
|[swap](#swap)|Troca os valores nesse objeto `basic_istringstream` por aqueles do objeto fornecido.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator=](#op_eq)|Atribui os valores a esse objeto `basic_istringstream` do parâmetro de objeto.|  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** \<sstream>  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>  basic_istringstream::allocator_type  
 O tipo é um sinônimo do parâmetro de modelo `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_istringstream"></a>  basic_istringstream::basic_istringstream  
 Constrói um objeto do tipo `basic_istringstream`.  
  
```  
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 `_Mode`  
 Uma das enumerações em [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 Um objeto do tipo `basic_string`.  
  
 `right`  
 Uma referência rvalue de um objeto `basic_istringstream`.  
  
### <a name="remarks"></a>Comentários  
 O primeiro construtor inicializa a classe base chamando [basic_istream](../standard-library/basic-istream-class.md)( `sb`), em que `sb` é o objeto armazenado da classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>. Também inicializa `sb` chamando `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).  
  
 O segundo construtor inicializa a classe base chamando `basic_istream(sb)`. Também inicializa `sb` chamando `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`).  
  
 O terceiro construtor inicializa o objeto com o conteúdo de `right` tratado como uma referência rvalue.  
  
##  <a name="op_eq"></a>  basic_istringstream::operator=  
 Atribui os valores a esse objeto `basic_istringstream` do parâmetro de objeto.  
  
```  
basic_istringstream& operator=(basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Parâmetros  
 `right`  
 Uma referência rvalue a um objeto `basic_istringstream`.  
  
### <a name="remarks"></a>Comentários  
 O operador de membro substitui o conteúdo do objeto pelo conteúdo de `right`, tratado como uma atribuição de movimentação de referência rvalue.  
  
##  <a name="rdbuf"></a>  basic_istringstream::rdbuf  
 Retorna o endereço do buffer de fluxo armazenado do tipo **pointer** para [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Valor de retorno  
 O endereço do buffer de fluxo armazenado do tipo **pointer** para basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="example"></a>Exemplo  
  Consulte [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) para ver um exemplo que usa `rdbuf`.  
  
##  <a name="str"></a>  basic_istringstream::str  
 Define ou obtém o texto em um buffer de cadeia de caracteres sem alterar a posição de gravação.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;

 
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>Parâmetros  
 `_Newstr`  
 A nova cadeia de caracteres.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna um objeto da classe [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, cuja sequência controlada é uma cópia da sequência controlada por **\*this**.  
  
### <a name="remarks"></a>Comentários  
 A primeira função membro retorna [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). As segunda função membro chama `rdbuf` -> **str**( `_Newstr`).  
  
### <a name="example"></a>Exemplo  
  Consulte [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) para obter um exemplo que usa **str**.  
  
##  <a name="swap"></a>  basic_istringstream::swap  
 Troca os valores de dois objetos `basic_istringstream`.  
  
```  
void swap(basic_istringstream& right);
```  
  
### <a name="parameters"></a>Parâmetros  
  
|Parâmetro|Descrição|  
|---------------|-----------------|  
|`right`|Uma referência `lvalue` a um objeto `basic_istringstream`.|  
  
### <a name="remarks"></a>Comentários  
 A função membro troca os valores desse objeto e os valores de `right`.  
  
## <a name="see-also"></a>Consulte também  
 [Acesso Thread-Safe na Biblioteca Padrão C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Programação de iostream](../standard-library/iostream-programming.md)   
 [Convenções de iostreams](../standard-library/iostreams-conventions.md)
