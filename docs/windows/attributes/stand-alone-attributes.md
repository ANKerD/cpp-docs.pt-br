---
title: Atributos autônomos (COM C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b46b5c3b4750957c548becfcc5143f5eed858f71
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790102"
---
# <a name="stand-alone-attributes"></a>Atributos autônomos
Um atributo autônomo não funciona em uma palavra-chave C++, mas é mais parecido com uma linha de código. Declarações de atributo autônomo exigem um ponto e vírgula no final da linha.
  
|Atributo|Descrição|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Emite a cadeia de caracteres especificada, sem caracteres de aspas, para o arquivo de cabeçalho gerado.|
|[custom](custom-cpp.md)|Permite que você defina seu próprio atributo.|
|[db_command](db-command.md)|Cria um comando OLE DB.|
|[emitidl](emitidl.md)|Determina se todos os atributos IDL subsequentes serão processados e colocados no arquivo. idl gerado.|
|[idl_module](idl-module.md)|Especifica um ponto de entrada em uma DLL.|
|[idl_quote](idl-quote.md)|Permite que você use construções IDL que não têm suporte na versão atual do Visual C++ e fazer com que eles passam para o arquivo. idl gerado.|
|[import](import.md)|Especifica outro arquivo. idl, odl ou. h, que contém definições que você deseja fazer referência do seu arquivo. idl principal.|
|[importidl](importidl.md)|Insere o arquivo. idl especificado no arquivo. idl gerado|
|[importlib](importlib.md)|Torna os tipos que já foram compilados em outra biblioteca de tipos disponível para a biblioteca de tipos que está sendo criada.|
|[include](include-cpp.md)|Especifica um ou mais arquivos de cabeçalho a serem incluídos no arquivo. idl gerado.|
|[includelib](includelib-cpp.md)|Faz com que um arquivo. IDL ou. h a serem incluídos no arquivo. idl gerado.|
|[library_block](library-block.md)|Coloca uma construção de dentro do bloco de biblioteca do arquivo. idl.|
|[módulo](module-cpp.md)|Define o bloco de biblioteca no arquivo. idl.|
|[no_injected_text](no-injected-text.md)|Impede que o compilador injetando código como resultado do uso do atributo.|
|[pragma](pragma.md)|Emite a cadeia de caracteres especificada, sem os caracteres de aspas no arquivo. idl gerado.|
  
## <a name="see-also"></a>Consulte também

[Atributos por uso](attributes-by-usage.md)