---
title: Classe cObList | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs: C++
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8d4c14ebe2c2e9cb143d8c08ab2e8170a7cd0f5c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2017
---
# <a name="coblist-class"></a>Classe cObList
fSupports ordenados listas de não exclusivo `CObject` ponteiros acessíveis em sequência ou pelo ponteiro de valor.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
class CObList : public CObject  
```  
  
## <a name="members"></a>Membros  
  
### <a name="public-constructors"></a>Construtores públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CObList::CObList](#coblist)|Constrói uma lista vazia para `CObject` ponteiros.|  
  
### <a name="public-methods"></a>Métodos públicos  
  
|Nome|Descrição|  
|----------|-----------------|  
|[CObList::AddHead](#addhead)|Adiciona um elemento (ou todos os elementos em outra lista) para o início da lista (faz um novo cabeçalho).|  
|[CObList::AddTail](#addtail)|Adiciona um elemento (ou todos os elementos em outra lista) para o fim da lista (faz uma novo final).|  
|[CObList::Find](#find)|Obtém a posição de um elemento especificado pelo valor do ponteiro.|  
|[CObList::FindIndex](#findindex)|Obtém a posição de um elemento especificado por um índice com base em zero.|  
|[CObList::GetAt](#getat)|Obtém o elemento na posição especificada.|  
|[CObList::GetCount](#getcount)|Retorna o número de elementos nesta lista.|  
|[CObList::GetHead](#gethead)|Retorna o elemento principal da lista (não pode estar vazio).|  
|[CObList::GetHeadPosition](#getheadposition)|Retorna a posição do elemento principal da lista.|  
|[CObList::GetNext](#getnext)|Obtém o próximo elemento de iteração.|  
|[CObList::GetPrev](#getprev)|Obtém o elemento anterior para iteração.|  
|[CObList::GetSize](#getsize)|Retorna o número de elementos nesta lista.|  
|[CObList::GetTail](#gettail)|Retorna o elemento final da lista (não pode estar vazio).|  
|[CObList::GetTailPosition](#gettailposition)|Retorna a posição do elemento da parte final da lista.|  
|[CObList::InsertAfter](#insertafter)|Insere um novo elemento após uma posição determinada.|  
|[CObList::InsertBefore](#insertbefore)|Insere um novo elemento antes de uma determinada posição.|  
|[CObList::IsEmpty](#isempty)|Testes para a condição de lista vazia (sem elementos).|  
|[CObList::RemoveAll](#removeall)|Remove todos os elementos da lista.|  
|[CObList::RemoveAt](#removeat)|Remove um elemento nesta lista, especificada pela posição.|  
|[CObList::RemoveHead](#removehead)|Remove o elemento do cabeçalho da lista.|  
|[CObList::RemoveTail](#removetail)|Remove o elemento do final da lista.|  
|[CObList::SetAt](#setat)|Define o elemento na posição especificada.|  
  
## <a name="remarks"></a>Comentários  
 `CObList`listas se comportam como listas duplamente vinculada.  
  
 Uma variável do tipo **posição** é uma chave para a lista. Você pode usar um **posição** variável como um iterador para percorrer uma lista em sequência e um indicador para manter um lugar. Uma posição porém não é o mesmo que um índice.  
  
 Inserção de elemento é muito rápido no topo lista, ao final e em um conhecido **posição**. Uma pesquisa sequencial é necessária procurar um elemento por valor ou índice. A pesquisa pode ser lenta se a lista for longa.  
  
 A `CObList` incorpora a macro `IMPLEMENT_SERIAL` para suportar serialização e despejo de seus elementos. Se uma lista de `CObject` ponteiros são armazenados para um arquivo, com um operador de inserção sobrecarregado ou com o `Serialize` função de membro, cada `CObject` elemento é serializado por sua vez.  
  
 Se você precisar de um despejo do indivíduo `CObject` elementos na lista, você deve definir a profundidade do contexto de despejo para 1 ou superior.  
  
 Quando um `CObList` objeto é excluído, ou quando seus elementos são removidos, somente o `CObject` ponteiros são removidos, não os objetos que eles fazem referência.  
  
 Você pode derivar suas próprias classes de `CObList`. Sua nova classe de lista, projetada para armazenar ponteiros para objetos derivados de `CObject`, adiciona novos membros de dados e novas funções de membro. Observe que a lista resultante não é estritamente tipo seguro, pois ela permite que a inserção de qualquer `CObject` ponteiro.  
  
> [!NOTE]
>  Você deve usar o [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) macro na implementação de sua classe derivada, se você pretende serializar a lista.  
  
 Para obter mais informações sobre como usar `CObList`, consulte o artigo [coleções](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Hierarquia de herança  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** afxcoll.h  
  
##  <a name="addhead"></a>CObList::AddHead  
 Adiciona um novo elemento ou a lista de elementos para o início da lista.  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>Parâmetros  
 `newElement`  
 O `CObject` ponteiro a ser adicionado a essa lista.  
  
 `pNewList`  
 Um ponteiro para outro `CObList` lista. Os elementos no `pNewList` será adicionado a essa lista.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a primeira versão do **posição** valor do elemento recentemente inserido.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::AddHead`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSIÇÃO AddHead (void\***  `newElement` **);**<br /><br /> **void AddHead (CPtrList\***  `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSIÇÃO AddHead (const CString &** `newElement` **);**<br /><br /> **POSIÇÃO AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList\***  `pNewList` **);**|  
  
### <a name="remarks"></a>Comentários  
 A lista pode estar vazia antes da operação.  
  
### <a name="example"></a>Exemplo  
  Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="addtail"></a>CObList::AddTail  
 Adiciona um novo elemento ou a lista de elementos para o fim desta lista.  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>Parâmetros  
 `newElement`  
 O `CObject` ponteiro a ser adicionado a essa lista.  
  
 `pNewList`  
 Um ponteiro para outro `CObList` lista. Os elementos no `pNewList` será adicionado a essa lista.  
  
### <a name="return-value"></a>Valor de retorno  
 Retorna a primeira versão do **posição** valor do elemento recentemente inserido.  
  
### <a name="remarks"></a>Comentários  
 A lista pode estar vazia antes da operação.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::AddTail`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSIÇÃO AddTail (void\***  `newElement` **);**<br /><br /> **void AddTail (CPtrList\***  `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSIÇÃO AddTail (const CString &** `newElement` **);**<br /><br /> **POSIÇÃO AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList\***  `pNewList` **);**|  
  
### <a name="example"></a>Exemplo  
  Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="coblist"></a>CObList::CObList  
 Constrói um vazio `CObject` lista de ponteiro.  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parâmetros  
 `nBlockSize`  
 A granularidade de alocação de memória para estender a lista.  
  
### <a name="remarks"></a>Comentários  
 À medida que aumenta a lista, a memória é alocada em unidades de `nBlockSize` entradas. Se uma alocação de memória falhar, um `CMemoryException` é gerada.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::CObList`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Exemplo  
  Abaixo está uma lista da `CObject`-classe derivada `CAge` usado em todos os exemplos de coleção:  
  
 [!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 Abaixo está um exemplo de `CObList` uso do construtor:  
  
 [!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="find"></a>CObList::Find  
 Pesquisa a lista em sequência para localizar o primeiro `CObject` ponteiro correspondente especificado `CObject` ponteiro.  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `searchValue`  
 O ponteiro de objeto a ser localizado na lista.  
  
 `startAfter`  
 A posição inicial da pesquisa.  
  
### <a name="return-value"></a>Valor de retorno  
 Um **posição** valor que pode ser usado para iteração ou recuperação de ponteiro de objeto; **Nulo** se o objeto não foi encontrado.  
  
### <a name="remarks"></a>Comentários  
 Observe que os valores de ponteiro são comparados, não o conteúdo dos objetos.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::Find`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Localização de posição (void\***  `searchValue` **, posição** `startAfter` **= NULL) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Localização de posição (LPCTSTR** `searchValue` **, posição** `startAfter` **= NULL) const;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="findindex"></a>CObList::FindIndex  
 Usa o valor de `nIndex` como um índice na lista.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `nIndex`  
 O índice de base zero do elemento de lista a ser localizado.  
  
### <a name="return-value"></a>Valor de retorno  
 Um **posição** valor que pode ser usado para iteração ou recuperação de ponteiro de objeto; **Nulo** se `nIndex` é muito grande. (A estrutura gera uma asserção se `nIndex` for negativo.)  
  
### <a name="remarks"></a>Comentários  
 Iniciar uma verificação sequencial do início da lista, parando o  *n* elemento th.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::FindIndex`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSIÇÃO FindIndex (INT_PTR** `nIndex` **) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSIÇÃO FindIndex (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="getat"></a>CObList::GetAt  
 Uma variável do tipo **posição** é uma chave para a lista.  
  
```  
CObject*& GetAt(POSITION position);  
const CObject*& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 *posição*  
 Um **posição** valor retornado pelo anterior `GetHeadPosition` ou **localizar** chamada de função de membro.  
  
### <a name="return-value"></a>Valor de retorno  
 Consulte a descrição do valor de retorno para [GetHead](#gethead).  
  
### <a name="remarks"></a>Comentários  
 Não é o mesmo que um índice, e você não pode operar em um **posição** valor por conta própria. `GetAt`recupera o `CObject` ponteiro associado com uma posição determinada.  
  
 Você deve garantir que seu **posição** valor representa uma posição válida na lista. Se ele for inválido, declara a versão de depuração da biblioteca Microsoft Foundation Class.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetAt`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void const\*& GetAt (posição** *posição* **) const;**<br /><br /> **void\*& GetAt (posição** *posição* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const CString & GetAt (posição** *posição* **) const;**<br /><br /> **CString & GetAt (posição** *posição* **);**|  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [FindIndex](#findindex).  
  
##  <a name="getcount"></a>CObList::GetCount  
 Obtém o número de elementos nesta lista.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um valor inteiro que contém a contagem de elementos.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetCount`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**() GetCount INT_PTR const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**() GetCount INT_PTR const;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="gethead"></a>CObList::GetHead  
 Obtém o `CObject` ponteiro que representa o elemento principal desta lista.  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Se a lista é acessada por meio de um ponteiro para um **CObList const**, em seguida, `GetHead` retorna um `CObject` ponteiro. Isso permite que a função a ser usada apenas no lado direito de uma instrução de atribuição e, portanto, protege a lista de modificação.  
  
 Se a lista é acessada diretamente ou através de um ponteiro para um `CObList`, em seguida, `GetHead` retorna uma referência a um `CObject` ponteiro. Isso permite que a função a ser usado em ambos os lados de uma instrução de atribuição e, portanto, permite que as entradas da lista a ser modificada.  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `GetHead`. Se a lista estiver vazia, a versão de depuração da biblioteca de classes Microsoft Foundation declara. Use [IsEmpty](#isempty) para verificar se a lista contém elementos.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetHead`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void const\*& (GetHead) const; void\*& () GetHead;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const CString & GetHead () const; CString & GetHead ();**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 O exemplo a seguir ilustra o uso de `GetHead` no lado esquerdo de uma instrução de atribuição.  
  
 [!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="getheadposition"></a>CObList::GetHeadPosition  
 Obtém a posição do elemento principal desta lista.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um **posição** valor que pode ser usado para iteração ou recuperação de ponteiro de objeto; **Nulo** se a lista está vazia.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetHeadPosition`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSICIONAR GetHeadPosition () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSICIONAR GetHeadPosition () const;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="getnext"></a>CObList::GetNext  
 Obtém o elemento de lista, identificado pelo `rPosition`, em seguida, define `rPosition` para o `POSITION` valor da próxima entrada na lista.  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `rPosition`  
 Uma referência a um `POSITION` valor retornado pelo anterior `GetNext`, `GetHeadPosition`, ou outra chamada de função de membro.  
  
### <a name="return-value"></a>Valor de retorno  
 Consulte a descrição do valor de retorno para [GetHead](#gethead).  
  
### <a name="remarks"></a>Comentários  
 Você pode usar `GetNext` em um loop de interação direta se estabelecer a posição inicial com uma chamada para `GetHeadPosition` ou `Find`.  
  
 Você deve garantir que seu `POSITION` valor representa uma posição válida na lista. Se ele for inválido, declara a versão de depuração da biblioteca Microsoft Foundation Class.  
  
 Se o elemento recuperado é o último na lista, em seguida, o novo valor de `rPosition` é definido como `NULL`.  
  
 É possível remover um elemento durante uma iteração. Consulte o exemplo para [RemoveAt](#removeat).  
  
> [!NOTE]
>  A partir de MFC 8.0 a versão const desse método foi alterada para retornar `const CObject*` em vez de `const CObject*&`.  Essa alteração foi feita para trazer o compilador em conformidade com o C++ padrão.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetNext`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Exemplo  
  Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="getprev"></a>CObList::GetPrev  
 Obtém o elemento de lista, identificado pelo `rPosition`, em seguida, define `rPosition` para o `POSITION` valor da entrada anterior na lista.  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parâmetros  
 `rPosition`  
 Uma referência a um `POSITION` valor retornado pelo anterior `GetPrev` ou outra chamada de função de membro.  
  
### <a name="return-value"></a>Valor de retorno  
 Consulte a descrição do valor de retorno para [GetHead](#gethead).  
  
### <a name="remarks"></a>Comentários  
 Você pode usar `GetPrev` em um loop de iteração inversa se estabelecer a posição inicial com uma chamada para `GetTailPosition` ou `Find`.  
  
 Você deve garantir que seu `POSITION` valor representa uma posição válida na lista. Se ele for inválido, declara a versão de depuração da biblioteca Microsoft Foundation Class.  
  
 Se o elemento recuperado é o primeiro na lista, em seguida, o novo valor de `rPosition` é definido como `NULL`.  
  
> [!NOTE]
>  A partir de MFC 8.0 a versão const desse método foi alterada para retornar `const CObject*` em vez de `const CObject*&`.  Essa alteração foi feita para trazer o compilador em conformidade com o C++ padrão.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetPrev`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Exemplo  
  Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="getsize"></a>CObList::GetSize  
 Retorna o número de elementos da lista.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 O número de itens na lista.  
  
### <a name="remarks"></a>Comentários  
 Chame esse método para recuperar o número de elementos na lista.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetSize`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**() GetSize INT_PTR const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**() GetSize INT_PTR const;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="gettail"></a>CObList::GetTail  
 Obtém o `CObject` ponteiro que representa o elemento final desta lista.  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Consulte a descrição do valor de retorno para [GetHead](#gethead).  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `GetTail`. Se a lista estiver vazia, a versão de depuração da biblioteca de classes Microsoft Foundation declara. Use [IsEmpty](#isempty) para verificar se a lista contém elementos.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetTail`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void const\*& (GetTail) const; void\*& () GetTail;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const CString & GetTail () const; CString & GetTail ();**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="gettailposition"></a>CObList::GetTailPosition  
 Obtém a posição do elemento final desta lista; **Nulo** se a lista está vazia.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um **posição** valor que pode ser usado para iteração ou recuperação de ponteiro de objeto; **Nulo** se a lista está vazia.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::GetTailPosition`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSICIONAR GetTailPosition () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSICIONAR GetTailPosition () const;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="insertafter"></a>CObList::InsertAfter  
 Adiciona um elemento a essa lista depois do elemento na posição especificada.  
  
```  
POSITION InsertAfter(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parâmetros  
 *posição*  
 Um **posição** valor retornado pelo anterior `GetNext`, `GetPrev`, ou **localizar** chamada de função de membro.  
  
 `newElement`  
 O ponteiro de objeto a ser adicionado a essa lista.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::InsertAfter`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSIÇÃO InsertAfter (posição** *posição* **, void\***  `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSIÇÃO InsertAfter (posição** *posição* **, CString const &** `newElement` **);**<br /><br /> **POSIÇÃO InsertAfter (posição** *posição* **, LPCTSTR** `newElement` **);**|  
  
### <a name="return-value"></a>Valor de retorno  
 Um **posição** valor que é o mesmo como o *posição* parâmetro.  
  
### <a name="example"></a>Exemplo  
  Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="insertbefore"></a>CObList::InsertBefore  
 Adiciona um elemento a essa lista antes do elemento na posição especificada.  
  
```  
POSITION InsertBefore(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parâmetros  
 *posição*  
 Um **posição** valor retornado pelo anterior `GetNext`, `GetPrev`, ou **localizar** chamada de função de membro.  
  
 `newElement`  
 O ponteiro de objeto a ser adicionado a essa lista.  
  
### <a name="return-value"></a>Valor de retorno  
 Um **posição** valor que pode ser usado para iteração ou recuperação de ponteiro de objeto; **Nulo** se a lista está vazia.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::InsertBefore`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**POSIÇÃO InsertBefore (posição** *posição* **, void\***  `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSIÇÃO InsertBefore (posição** *posição* **, CString const &** `newElement` **);**<br /><br /> **POSIÇÃO InsertBefore (posição** *posição* **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Exemplo  
  Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="isempty"></a>CObList::IsEmpty  
 Indica se esta lista não contém elementos.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Valor de retorno  
 Diferente de zero se a lista estiver vazia; Caso contrário, 0.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::IsEmpty`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL (de) de IsEmpty const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL (de) de IsEmpty const;**|  
  
### <a name="example"></a>Exemplo  
  Consulte o exemplo para [RemoveAll](#removeall).  
  
##  <a name="removeall"></a>CObList::RemoveAll  
 Remove todos os elementos da lista e libera associado `CObList` memória.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Comentários  
 Nenhum erro será gerado se a lista já está vazia.  
  
 Quando você remove elementos de um `CObList`, remova os ponteiros do objeto da lista. É sua responsabilidade para excluir os próprios objetos.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::RemoveAll`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void () RemoveAll;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void () RemoveAll;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="removeat"></a>CObList::RemoveAt  
 Remove o elemento especificado da lista.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Parâmetros  
 *posição*  
 A posição do elemento a ser removido da lista.  
  
### <a name="remarks"></a>Comentários  
 Quando você remove um elemento de um `CObList`, remova o ponteiro de objeto da lista. É sua responsabilidade para excluir os próprios objetos.  
  
 Você deve garantir que seu **posição** valor representa uma posição válida na lista. Se ele for inválido, declara a versão de depuração da biblioteca Microsoft Foundation Class.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::RemoveAt`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (posição** *posição* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (posição** *posição* **);**|  
  
### <a name="example"></a>Exemplo  
  Tenha cuidado ao remover um elemento durante uma iteração de lista. O exemplo a seguir mostra uma técnica de remoção que garante uma válido **posição** valor para [GetNext](#getnext).  
  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="removehead"></a>CObList::RemoveHead  
 Remove o elemento do cabeçalho da lista e retorna um ponteiro para ele.  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>Valor de retorno  
 O `CObject` ponteiro anteriormente no topo da lista.  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `RemoveHead`. Se a lista estiver vazia, a versão de depuração da biblioteca de classes Microsoft Foundation declara. Use [IsEmpty](#isempty) para verificar se a lista contém elementos.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::RemoveHead`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* () RemoveHead;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**() CString RemoveHead;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="removetail"></a>CObList::RemoveTail  
 Remove o elemento do final da lista e retorna um ponteiro para ele.  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>Valor de retorno  
 Um ponteiro para o objeto que estava no final da lista.  
  
### <a name="remarks"></a>Comentários  
 Certifique-se de que a lista não está vazia antes de chamar `RemoveTail`. Se a lista estiver vazia, a versão de depuração da biblioteca de classes Microsoft Foundation declara. Use [IsEmpty](#isempty) para verificar se a lista contém elementos.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::RemoveTail`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* () RemoveTail;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**() CString RemoveTail;**|  
  
### <a name="example"></a>Exemplo  
 Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="setat"></a>CObList::SetAt  
 Define o elemento na posição especificada.  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parâmetros  
 `pos`  
 O **posição** do elemento a ser definido.  
  
 `newElement`  
 O `CObject` ponteiro a ser gravado para a lista.  
  
### <a name="remarks"></a>Comentários  
 Uma variável do tipo **posição** é uma chave para a lista. Não é o mesmo que um índice, e você não pode operar em um **posição** valor por conta própria. `SetAt`grava o `CObject` ponteiro para a posição especificada na lista.  
  
 Você deve garantir que seu **posição** valor representa uma posição válida na lista. Se ele for inválido, declara a versão de depuração da biblioteca Microsoft Foundation Class.  
  
 A tabela a seguir mostra outro membro funções que são semelhantes às `CObList::SetAt`.  
  
|Classe|Função membro|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (posição** `pos` **, CString const &** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt (posição** `pos` **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Exemplo  
  Consulte [CObList::CObList](#coblist) para obter uma lista da `CAge` classe.  
  
 [!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 Os resultados desse programa são da seguinte maneira:  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>Consulte também  
 [Classe CObject](../../mfc/reference/cobject-class.md)   
 [Gráfico de hierarquia](../../mfc/hierarchy-chart.md)   
 [Classe CStringList](../../mfc/reference/cstringlist-class.md)   
 [Classe de CPtrList](../../mfc/reference/cptrlist-class.md)