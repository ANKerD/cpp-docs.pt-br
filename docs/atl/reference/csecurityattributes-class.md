---
title: Classe CSecurityAttributes | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
dev_langs:
- C++
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 672da1c98ebc51a7440e29234950be2adb5e1c0e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093036"
---
# <a name="csecurityattributes-class"></a>Classe CSecurityAttributes

Essa classe é um wrapper fino em que a estrutura de atributos de segurança.

> [!IMPORTANT]
>  Essa classe e seus membros não podem ser usados em aplicativos executados no tempo de execução do Windows.

## <a name="syntax"></a>Sintaxe

```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```

## <a name="members"></a>Membros

### <a name="public-constructors"></a>Construtores Públicos

|Nome|Descrição|
|----------|-----------------|
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|O construtor.|

### <a name="public-methods"></a>Métodos públicos

|Nome|Descrição|
|----------|-----------------|
|[CSecurityAttributes::Set](#set)|Chame esse método para definir os atributos do `CSecurityAttributes` objeto.|

## <a name="remarks"></a>Comentários

O `SECURITY_ATTRIBUTES` estrutura contém uma [descritor de segurança](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) usada para a criação de um objeto e especifica se o identificador recuperado especificando essa estrutura é herdável.

Para obter uma introdução ao modelo de controle de acesso no Windows, consulte [controle de acesso](/windows/desktop/SecAuthZ/access-control) no SDK do Windows.

## <a name="inheritance-hierarchy"></a>Hierarquia de herança

`SECURITY_ATTRIBUTES`

`CSecurityAttributes`

## <a name="requirements"></a>Requisitos

**Cabeçalho:** atlsecurity. h

##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes

O construtor.

```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```

### <a name="parameters"></a>Parâmetros

*rSecurityDescriptor*<br/>
Referência a um descritor de segurança.

*bInheritsHandle*<br/>
Especifica se o identificador retornado é herdado quando um novo processo é criado. Se esse membro for true, o novo processo herda o identificador.

##  <a name="set"></a>  CSecurityAttributes::Set

Chame esse método para definir os atributos do `CSecurityAttributes` objeto.

```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```

### <a name="parameters"></a>Parâmetros

*rSecurityDescriptor*<br/>
Referência a um descritor de segurança.

*bInheritHandle*<br/>
Especifica se o identificador retornado é herdado quando um novo processo é criado. Se esse membro for true, o novo processo herda o identificador.

### <a name="remarks"></a>Comentários

Esse método é usado pelo construtor para inicializar o `CSecurityAttributes` objeto.

## <a name="see-also"></a>Consulte também

[Exemplo de segurança](../../visual-cpp-samples.md)<br/>
[SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)<br/>
[descritor de segurança](/windows/desktop/api/winnt/ns-winnt-_security_descriptor)<br/>
[Visão geral da classe](../../atl/atl-class-overview.md)<br/>
[Funções globais de segurança](../../atl/reference/security-global-functions.md)
