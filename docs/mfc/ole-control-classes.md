---
title: Classes de controle OLE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad9ab489506964266b28a38563c366db2b0d54fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439075"
---
# <a name="ole-control-classes"></a>Classes de controle OLE

Essas são as classes principais usadas ao escrever controles OLE. O `COleControlModule` classe em um módulo de controle OLE é como o [CWinApp](../mfc/reference/cwinapp-class.md) classe em um aplicativo. Cada módulo implementa um ou mais controles OLE; Esses controles são representados por `COleControl` objetos. Esses controles se comunicar com seus contêineres usando `CConnectionPoint` objetos.

O `CPictureHolder` e `CFontHolder` classes encapsulam interfaces COM para imagens e fontes, enquanto o `COlePropertyPage` e `CPropExchange` classes ajudam você a implementar as páginas de propriedade e persistência de propriedade para o seu controle.

[COleControlModule](../mfc/reference/colecontrolmodule-class.md)<br/>
Substitui o `CWinApp` classe para o seu módulo de controle OLE. Derivar o `COleControlModule` classe para desenvolver um objeto de módulo de controle OLE. Ele fornece funções de membro para inicializar o módulo do seu controle OLE.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
Derivar o `COleControl` classe para desenvolver um controle OLE. Derivada de `CWnd`, essa classe herda toda a funcionalidade de um objeto de janela do Windows além de funcionalidades específicas do OLE adicionais, como o acionamento do evento e a capacidade de dar suporte a métodos e propriedades.

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
O `CConnectionPoint` classe define um tipo especial de interface usada para se comunicar com outros objetos OLE, chamados de ponto de conexão. Um ponto de conexão implementa uma interface de saída que é capaz de iniciar as ações de outros objetos, como disparar eventos e notificações de alteração.

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Encapsula a funcionalidade de um objeto de imagem do Windows e o `IPicture` COM interface; usado para implementar a propriedade de imagem personalizada de um controle OLE.

[CFontHolder](../mfc/reference/cfontholder-class.md)<br/>
Encapsula a funcionalidade de um objeto de fonte do Windows e o `IFont` COM interface; usado para implementar a propriedade de fonte de estoque de um controle OLE.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
Exibe as propriedades de uma OLE controlam em uma interface gráfica, semelhante a uma caixa de diálogo.

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
Oferece suporte à implementação de persistência da propriedade para seus controles OLE. Análogo à [CDataExchange](../mfc/reference/cdataexchange-class.md) para caixas de diálogo.

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
Usa um identificador de origem, ou uma representação de cadeia de caracteres que ele pode fazer em um identificador de origem e associá-lo de forma síncrona no fluxo para o qual o moniker é um nome.

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
Funciona da mesma forma que `CMonikerFile`; no entanto, ele associa o moniker assincronamente para o fluxo para o qual o moniker é um nome.

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
Implementa uma controle OLE propriedade que pode ser carregada de forma assíncrona.

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
Implementa uma controle OLE transferida de forma assíncrona e armazenada em cache em um arquivo de memória de propriedade.

[COleCmdUI](../mfc/reference/colecmdui-class.md)<br/>
Permite que um documento ativo receber comandos que se originam na interface do usuário do seu contêiner (por exemplo, FileNew, abrir, imprimir e assim por diante) e permite que um contêiner receber comandos que se originam na interface do usuário do documento ativo.

[COleSafeArray](../mfc/reference/colesafearray-class.md)<br/>
Funciona com matrizes de tipo arbitrário e dimensão.

## <a name="see-also"></a>Consulte também

[Visão geral da classe](../mfc/class-library-overview.md)

