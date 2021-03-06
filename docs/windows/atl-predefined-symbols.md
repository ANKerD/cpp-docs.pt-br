---
title: Símbolos predefinidos ATL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 965eb339295b86c223b5081dede8e33dd282b95d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386594"
---
# <a name="atl-predefined-symbols"></a>Símbolos predefinidos ATL

Esses símbolos são definidos nos arquivos de cabeçalho da ATL, mas eles oferecem suporte a ações e funções de aplicativo do Windows padrão. Esses símbolos são usados principalmente com caixas de diálogo. Quando você estiver trabalhando com caixas de diálogo e controles na [editor de caixa de diálogo](../windows/dialog-editor.md), esses símbolos aparecerá na **propriedades** janela associada com controles comuns. Por exemplo, se a caixa de diálogo tem um **Cancelar** botão, que o comando será associado com o símbolo IDCANCEL na [janela propriedades](/visualstudio/ide/reference/properties-window).

|||
|-|-|
|IDABORT|Controle: Botão de anulação de caixa de diálogo|
|IDC_STATIC|Controle: Controle estático|
|IDCANCEL|Controle: Botão de cancelamento de caixa de diálogo|
|IDIGNORE|Controle: Botão de ignorar de caixa de diálogo|
|IDNO|Controle: não caixa de diálogo nenhum botão|
|IDOK|Controle: Botão de Okey da caixa de diálogo|
|IDR_ACCELERATOR1|Recurso: Tabela de aceleradores|
|IDRETRY|Controle: Botão de repetição de caixa de diálogo|
|IDS_PROJNAME|Cadeia de caracteres: Nome do aplicativo atual|
|IDYES|Controle: Caixa de diálogo Sim botão|

## <a name="requirements"></a>Requisitos

ATL

## <a name="see-also"></a>Consulte também

[IDs de símbolos predefinidos](../windows/predefined-symbol-ids.md)<br/>
[Símbolos: identificadores de recursos](../windows/symbols-resource-identifiers.md)