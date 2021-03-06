---
title: Classe IRowsetNotifyImpl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
- IRowsetNotifyImpl::OnRowChange
- IRowsetNotifyImpl.OnRowChange
- OnRowChange
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
- OnFieldChange method
- OnRowChange method
- OnRowsetChange method
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d2d63b4046774bd7e1c427639db3483536e94bc5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095333"
---
# <a name="irowsetnotifyimpl-class"></a>Classe IRowsetNotifyImpl

Implementa e registra [IRowsetNotify](/previous-versions/windows/desktop/ms712959\(v=vs.85\)) no consumidor (também conhecido como o "coletor") para que ele pode manipular notificações.  
  
## <a name="syntax"></a>Sintaxe

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  

## <a name="requirements"></a>Requisitos  

**Cabeçalho:** atldbcli.h  
  
## <a name="members"></a>Membros  
  
### <a name="methods"></a>Métodos  
  
|||  
|-|-|  
|[OnFieldChange](#onfieldchange)|Notifica o consumidor sobre qualquer alteração no valor de uma coluna.|  
|[OnRowChange](#onrowchange)|Notifica o consumidor sobre a primeira alteração em uma linha ou sobre qualquer alteração que afete toda a linha.|  
|[OnRowsetChange](#onrowsetchange)|Notifica o consumidor sobre qualquer alteração que afete todo o conjunto de linhas.|  
  
## <a name="remarks"></a>Comentários  

Ver [recebendo notificações](../../data/oledb/receiving-notifications.md) sobre como implementar a interface de ponto de conexão no consumidor.  
  
`IRowsetNotifyImpl` Fornece uma implementação fictícia para `IRowsetNotify`, com funções vazias para o `IRowsetNotify` métodos [OnFieldChange](/previous-versions/windows/desktop/ms715961\(v=vs.85\)), [OnRowChange](/previous-versions/windows/desktop/ms722694\(v=vs.85\)), e [OnRowsetChange](/previous-versions/windows/desktop/ms722669\(v=vs.85\)). Se você herdar desta classe quando você implementa um `IRowsetNotify` interface, você pode implementar métodos necessários. Você também precisará fornecer implementações vazias para os outros métodos por conta própria.  

## <a name="onfieldchange"></a> Irowsetnotifyimpl:: Onfieldchange

Notifica o consumidor sobre qualquer alteração no valor de uma coluna.  
  
### <a name="syntax"></a>Sintaxe  
  
```cpp
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parâmetros  

Ver [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961\(v=vs.85\)) para descrições de parâmetro.  
  
### <a name="return-value"></a>Valor de retorno  

Ver [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961\(v=vs.85\)) para descrições de valor de retorno.  
  
### <a name="remarks"></a>Comentários  

Este método encapsula o [IRowsetNotify::OnFieldChange](/previous-versions/windows/desktop/ms715961\(v=vs.85\)) método. Consulte a descrição desse método na referência do OLE DB do programador para obter detalhes.  

## <a name="onrowchange"></a> Irowsetnotifyimpl:: Onrowchange

Notifica o consumidor sobre a primeira alteração em uma linha ou sobre qualquer alteração que afete toda a linha.  
  
### <a name="syntax"></a>Sintaxe  
  
```cpp
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parâmetros  

Ver [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694\(v=vs.85\)) para descrições de parâmetro.  
  
### <a name="return-value"></a>Valor de retorno  

Ver [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694\(v=vs.85\)) para descrições de valor de retorno.  
  
### <a name="remarks"></a>Comentários  

Este método encapsula o [IRowsetNotify::OnRowChange](/previous-versions/windows/desktop/ms722694\(v=vs.85\)) método. Consulte a descrição desse método na referência do OLE DB do programador para obter detalhes. 

## <a name="onrowsetchange"></a> Irowsetnotifyimpl:: Onrowsetchange

Notifica o consumidor sobre qualquer alteração que afete todo o conjunto de linhas.  
  
### <a name="syntax"></a>Sintaxe  
  
```cpp
STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parâmetros  

Ver [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669\(v=vs.85\)) para descrições de parâmetro.  
  
### <a name="return-value"></a>Valor de retorno  

Ver [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669\(v=vs.85\)) para descrições de valor de retorno.  
  
### <a name="remarks"></a>Comentários  

Este método encapsula o [IRowsetNotify::OnRowsetChange](/previous-versions/windows/desktop/ms722669\(v=vs.85\)) método. Consulte a descrição desse método na referência do OLE DB do programador para obter detalhes.
  
## <a name="see-also"></a>Consulte também  

[Modelos de consumidor do OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Modelos de consumidor do OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[IRowsetNotify](/previous-versions/windows/desktop/ms712959\(v=vs.85\))   
[Classe IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)