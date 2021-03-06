---
title: Desabilitando guias | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- guides, disabling snapping
- Dialog editor [C++], snap to guides
- snap to guides (Dialog editor)
- controls [C++], snap to guides/grid
ms.assetid: 51efa07b-8684-474e-a0b4-191ec5d91d1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35c552a6bb384f87c358ba25a945a7f02cc30114
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380796"
---
# <a name="disabling-guides"></a>Desabilitando guias

Você pode usar chaves especiais em conjunto com o mouse para desabilitar o efeito dos guias de ajuste. Usando o **Alt** chave desativa os efeitos de ajuste do guia selecionada. Movendo um guia com o **Shift** chave impede que os controles sem-instantâneo movendo com o guia.

### <a name="to-disable-the-snapping-effect-of-the-guides"></a>Para desabilitar o efeito dos guias de ajuste

1. Arraste o controle enquanto mantém pressionada a **Alt** chave.

### <a name="to-move-guides-without-moving-the-snapped-controls"></a>Para mover guias sem mover os controles sem-instantâneo

1. Arraste a guia enquanto mantém pressionada a **Shift** chave.

### <a name="to-turn-off-the-guides"></a>Para desativar os guias

1. Dos **formato** menu, escolha **guia de configurações**.

2. No [guia de caixa de diálogo de configurações](../windows/guide-settings-dialog-box.md), em **guias de Layout**, selecione **None**.

   > [!NOTE]
   > Você também pode clicar duas vezes a barra de régua para acessar o **guia de configurações** caixa de diálogo.

\- ou -

- Sobre o **formato** menu, clique em **ativar/desativar guias**.

Para obter informações sobre como adicionar recursos a projetos gerenciados, consulte [recursos em aplicativos de área de trabalho](/dotnet/framework/resources/index) na *guia do desenvolvedor do .NET Framework*. Para obter informações sobre como adicionar manualmente os arquivos de recursos a projetos gerenciados, acessar recursos, exibir recursos estáticos e atribuir cadeias de caracteres de recurso a propriedades, consulte [criando arquivos de recursos para aplicativos de área de trabalho](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obter informações sobre globalização e localização de recursos em aplicativos gerenciados, consulte [Globalizing e Localizando aplicativos do .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Win32

## <a name="see-also"></a>Consulte também

[Estados do Editor de Caixa de Diálogo (guias e grades)](../windows/dialog-editor-states-guides-and-grids.md)<br/>
[Controles em caixas de diálogo](../windows/controls-in-dialog-boxes.md)