---
title: -INTEGRITYCHECK (Exigir verificação de assinatura) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2975f9648415b072c7e0cc893183b4a7880c3e43
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444899"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (exigir verificação de assinatura)

Especifica que a assinatura digital da imagem binária deve ser verificada em tempo de carregamento.

```
/INTEGRITYCHECK[:NO]
```

## <a name="remarks"></a>Comentários

Por padrão, **/INTEGRITYCHECK** está desativado.

O **/INTEGRITYCHECK** conjuntos de opções — no cabeçalho PE do arquivo executável ou arquivo DLL — um sinalizador para o Gerenciador de memória verificar se há uma assinatura digital para carregar a imagem no Windows. Essa opção deve ser definida para DLLs de 32 bits e 64 bits que implementam o código de modo de kernel carregado por determinados recursos do Windows e é recomendada para todos os drivers de dispositivo no Windows Vista, Windows 7, Windows 8, Windows Server 2008 e Windows Server 2012. Versões do Windows anteriores ao Windows Vista ignoram este sinalizador. Para obter mais informações, consulte [forçado integridade de assinatura de arquivos portáteis executáveis (PE)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).

### <a name="to-set-this-linker-option-in-visual-studio"></a>Para definir essa opção do vinculador no Visual Studio

1. Abra o projeto **páginas de propriedade** caixa de diálogo. Para obter mais informações, confira [Trabalhando com propriedades do projeto](../../ide/working-with-project-properties.md).

1. Expanda o nó **Propriedades de Configuração**.

1. Expanda o **vinculador** nó.

1. Selecione o **linha de comando** página de propriedades.

1. Na **opções adicionais**, insira `/INTEGRITYCHECK` ou `/INTEGRITYCHECK:NO`.

## <a name="see-also"></a>Consulte também

[Definindo opções de vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opções do vinculador](../../build/reference/linker-options.md)<br/>
[Arquivos de integridade de assinatura de PE (executável portátil) forçado](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)<br/>
[Instruções passo a passo de assinatura de código de modo kernel](https://msdn.microsoft.com/windows/hardware/gg487328.aspx)<br/>
[DLLs do AppInit no Windows 7 e Windows Server 2008](https://msdn.microsoft.com/windows/hardware/gg463040.aspx)