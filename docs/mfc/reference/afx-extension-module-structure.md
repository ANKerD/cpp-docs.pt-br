---
title: Estrutura AFX_EXTENSION_MODULE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98486078684fe4fa8da25dd8d0c78be96be70a08
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430352"
---
# <a name="afxextensionmodule-structure"></a>Estrutura AFX_EXTENSION_MODULE

O `AFX_EXTENSION_MODULE` é usado durante a inicialização de DLLs de extensão do MFC para manter o estado do módulo de DLL de extensão do MFC.

## <a name="syntax"></a>Sintaxe

```
struct AFX_EXTENSION_MODULE
{
    BOOL bInitialized;
    HMODULE hModule;
    HMODULE hResource;
    CRuntimeClass* pFirstSharedClass;
    COleObjectFactory* pFirstSharedFactory;
};
```

#### <a name="parameters"></a>Parâmetros

*bInitialized*<br/>
TRUE se o módulo DLL foi inicializado com `AfxInitExtensionModule`.

*hModule*<br/>
Especifica o identificador do módulo DLL.

*hResource*<br/>
Especifica o identificador do módulo de DLL de recurso personalizado.

*pFirstSharedClass*<br/>
Um ponteiro para informações (o `CRuntimeClass` estrutura) sobre a primeira classe de tempo de execução do módulo DLL. Usado para fornecer o início da lista de classe de tempo de execução.

*pFirstSharedFactory*<br/>
Um ponteiro para a primeira fábrica de objeto do módulo DLL (um `COleObjectFactory` objeto). Usado para fornecer o início da lista de classe de fábrica.

## <a name="remarks"></a>Comentários

Extensão MFC DLLs é preciso fazer duas coisas em seus `DllMain` função:

- Chame [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) e verifique o valor retornado.

- Criar uma `CDynLinkLibrary` do objeto se a DLL estiver exportando [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) objetos ou tem seus próprios recursos personalizados.

O `AFX_EXTENSION_MODULE` estrutura é usada para manter uma cópia do estado do módulo DLL, incluindo uma cópia dos objetos de classe de tempo de execução que foram inicializados pela DLL de extensão de MFC como parte da construção de objeto estático normal executada antes de extensão do MFC `DllMain` é inserido. Por exemplo:

[!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]

As informações de módulo armazenadas em do `AFX_EXTENSION_MODULE` estrutura pode ser copiada para o `CDynLinkLibrary` objeto. Por exemplo:

[!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]

## <a name="requirements"></a>Requisitos

**Cabeçalho:** AFX. h

## <a name="see-also"></a>Consulte também

[Estruturas, estilos, retornos de chamada e mapas de mensagem](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)<br/>
[AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

