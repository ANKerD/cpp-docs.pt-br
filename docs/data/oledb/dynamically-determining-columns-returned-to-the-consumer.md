---
title: Determinando dinamicamente colunas retornadas ao consumidor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d3b7d20fb82399f3778c751de28858b93f81071a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080877"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>Determinando dinamicamente colunas retornadas ao consumidor

As macros PROVIDER_COLUMN_ENTRY lidar normalmente com o `IColumnsInfo::GetColumnsInfo` chamar. No entanto, como um consumidor pode optar por usar indicadores, o provedor deve ser capaz de alterar as colunas retornadas, dependendo se o consumidor solicita um indicador.  
  
Para lidar com o `IColumnsInfo::GetColumnsInfo` chamar, exclua o PROVIDER_COLUMN_MAP, que define uma função `GetColumnInfo`, da `CAgentMan` usuário gravar em myproviderrs. H e substituí-lo com a definição para seu próprio `GetColumnInfo` função:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
Em seguida, implementar o `GetColumnInfo` funcionar em MyProviderRS.cpp, conforme mostrado no código a seguir.  
  
`GetColumnInfo` verifica primeiro se a propriedade do OLE DB `DBPROP_BOOKMARKS` está definido. Para obter a propriedade `GetColumnInfo` usa um ponteiro (`pRowset`) para o objeto de conjunto de linhas. O `pThis` ponteiro representa a classe que criou o conjunto de linhas, que é a classe em que o mapa de propriedade é armazenado. `GetColumnInfo` typecasts a `pThis` ponteiro para um `RMyProviderRowset` ponteiro.  
  
Para verificar se há o `DBPROP_BOOKMARKS` propriedade, `GetColumnInfo` usa o `IRowsetInfo` interface, que pode ser obtido chamando `QueryInterface` sobre o `pRowset` interface. Como alternativa, você pode usar uma ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) método em vez disso.  
  
```cpp
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
   // ordinal entry in the column map with the bookmark information.  
   CAgentRowset* pRowset = (CAgentRowset*) pThis;  
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spRowsetProps)  
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),   
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText)  
   ulCols++;  
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand2)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
```  
  
Este exemplo usa uma matriz estática para conter as informações de coluna. Se o consumidor não deseja que a coluna de indicador, uma entrada na matriz é não utilizada. Para lidar com as informações, você cria duas macros a matriz: ADD_COLUMN_ENTRY e ADD_COLUMN_ENTRY_EX. ADD_COLUMN_ENTRY_EX aceita um parâmetro extra, `flags`, que é necessário se você designar uma coluna de indicador.  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```  
  
No `GetColumnInfo` função, a macro de indicador é usada da seguinte forma:  
  
```cpp  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
Agora você pode compilar e executar o provedor aprimorado. Para testar o provedor, modifique o consumidor de teste, conforme descrito na [implementando um consumidor simples](../../data/oledb/implementing-a-simple-consumer.md). Execute o consumidor de teste com o provedor. Verifique se que o consumidor de teste recupera as cadeias de caracteres apropriadas do provedor quando você clica o **executar** botão na **testar consumidor** caixa de diálogo.  
  
## <a name="see-also"></a>Consulte também  

[Aprimorando o provedor somente leitura simples](../../data/oledb/enhancing-the-simple-read-only-provider.md)