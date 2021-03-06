---
title: Classe de CDocObjectServerItem | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- CDocObjectServerItem [MFC], CDocObjectServerItem
- CDocObjectServerItem [MFC], GetDocument
- CDocObjectServerItem [MFC], OnHide
- CDocObjectServerItem [MFC], OnShow
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5dad01bb73f04482b15e345451a0a4a6a069985
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396396"
---
# <a name="cdocobjectserveritem-class"></a>Classe de CDocObjectServerItem

Verbos de servidor OLE especificamente para servidores DocObject.

## <a name="syntax"></a>Sintaxe

```
class CDocObjectServerItem : public COleServerItem
```

## <a name="members"></a>Membros

### <a name="protected-constructors"></a>Construtores Protegidos

|Nome|Descrição|
|----------|-----------------|
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Constrói um objeto `CDocObjectServerItem`.|

### <a name="public-methods"></a>Métodos Públicos

|Nome|Descrição|
|----------|-----------------|
|[CDocObjectServerItem::GetDocument](#getdocument)|Recupera um ponteiro para o documento que contém o item.|

### <a name="protected-methods"></a>Métodos Protegidos

|Nome|Descrição|
|----------|-----------------|
|[CDocObjectServerItem::OnDoVerb](#ondoverb)|Gera uma exceção se o framework tenta ocultar um item DocObject.|
|[CDocObjectServerItem::OnHide](#onhide)|Gera uma exceção se o framework tenta ocultar um item DocObject.|
|[CDocObjectServerItem::OnShow](#onshow)|Chamado pelo framework para tornar o DocObject item in loco Active Directory. Se o item não for DocObject, chamadas [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|

## <a name="remarks"></a>Comentários

`CDocObjectServerItem` Define as funções de membro substituíveis: [OnHide](#onhide), [OnDoVerb](#ondoverb), e [OnShow](#onshow).

Para usar `CDocObjectServerItem`, garantem que o [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) substituir em seu `COleServerDoc`-classe derivada retorna um novo `CDocObjectServerItem` objeto. Se você precisar alterar qualquer funcionalidade no item, você pode criar uma nova instância da sua própria `CDocObjectServerItem`-classe derivada.

Para obter mais informações sobre DocObjects, consulte [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) e [COleCmdUI](../../mfc/reference/colecmdui-class.md) no *referência da MFC*.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocItem](../../mfc/reference/cdocitem-class.md)

[COleServerItem](../../mfc/reference/coleserveritem-class.md)

`CDocObjectServerItem`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** afxdocob.h

##  <a name="cdocobjectserveritem"></a>  CDocObjectServerItem::CDocObjectServerItem

Constrói um objeto `CDocObjectServerItem`.

```
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```

### <a name="parameters"></a>Parâmetros

*pServerDoc*<br/>
Um ponteiro para o documento que contém o novo item DocObject.

*bAutoDelete*<br/>
Indica se o objeto pode ser excluído quando um link para ele é liberado. Defina o argumento como FALSE se o `CDocObjectServerItem` objeto é uma parte integral de dados do seu documento. Defina como TRUE se o objeto é uma estrutura secundária usada para identificar um intervalo nos dados do documento que podem ser excluídos pela estrutura.

##  <a name="getdocument"></a>  CDocObjectServerItem::GetDocument

Recupera um ponteiro para o documento que contém o item.

```
COleServerDoc* GetDocument() const;
```

### <a name="return-value"></a>Valor de retorno

Um ponteiro para o documento que contém o item; NULL se o item não é parte de um documento.

### <a name="remarks"></a>Comentários

Isso permite o acesso ao documento no servidor que é passado como um argumento para o [CDocObjectServerItem](#cdocobjectserveritem) construtor.

##  <a name="onhide"></a>  CDocObjectServerItem::OnHide

Chamado pelo framework para ocultar o item.

```
virtual void OnHide();
```

### <a name="remarks"></a>Comentários

A implementação padrão gera uma exceção se o item for DocObject. Você não pode ocultar um item DocObject ativo porque ele usa a exibição inteira. Você deve desativar o item DocObject para fazê-la desaparecer. Se o item não for DocObject, a implementação padrão chama [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).

##  <a name="onshow"></a>  CDocObjectServerItem::OnShow

Chamado pelo framework para instruir o aplicativo de servidor para verificar o DocObject item in loco Active Directory.

```
virtual void OnShow();
```

### <a name="remarks"></a>Comentários

Se o item não for DocObject, a implementação padrão chama [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Substitua essa função se você quiser executar especial ao abrir um item DocObject de processamento.

## <a name="see-also"></a>Consulte também

[Classe COleServerItem](../../mfc/reference/coleserveritem-class.md)<br/>
[Gráfico da hierarquia](../../mfc/hierarchy-chart.md)<br/>
[Classe CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md)<br/>
[Classe COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)
