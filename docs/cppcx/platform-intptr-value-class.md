---
title: Classe de valor IntPtr | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
dev_langs:
- C++
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0c6f7bc2cdc6b1478aba26c1ce0db48464a9ef2
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104031"
---
# <a name="platformintptr-value-class"></a>Platform::classe de valor IntPtr

Representa um ponteiro ou um identificador assinado e cujo tamanho é específico de plataforma (32 bits ou 64 bits).

## <a name="syntax"></a>Sintaxe

```cpp
public value struct IntPtr
```

### <a name="members"></a>Membros

IntPtr tem os seguintes membros:

|Membro|Descrição|
|------------|-----------------|
|[IntPtr::IntPtr](#ctor)|Inicializa uma nova instância de IntPtr.|
|[Operador IntPtr::op_explicit](#op-explicit)|Converte o parâmetro especificado em um IntPtr ou um ponteiro para um valor de IntPtr.|
|[IntPtr::ToInt32](#toint32)|Converte o IntPtr atual em um número inteiro de 32 bits.|

### <a name="requirements"></a>Requisitos

**Mínimo de cliente com suporte:** Windows 8

**Mínimo de servidor com suporte:** Windows Server 2012

**Namespace:** Platform

**Metadados:** platform.winmd

## <a name="ctor"> </a> Construtor IntPtr::IntPtr

Inicializa uma nova instância de um IntPtr com o valor especificado.

### <a name="syntax"></a>Sintaxe

```cpp
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );
```

### <a name="parameters"></a>Parâmetros

*value*<br/>
Um identificador ou um ponteiro de 64 bits ou um ponteiro para um valor de 64 bits ou um valor de 32 bits que pode ser convertido em um valor de 64 bits.

## <a name="op-explicit"> </a> Operador IntPtr::op_explicit

Converte o parâmetro especificado em um IntPtr ou um ponteiro para um valor de IntPtr.

### <a name="syntax"></a>Sintaxe

```cpp
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );
```

### <a name="parameters"></a>Parâmetros

*Valor1*<br/>
Um ponteiro para um identificador ou IntPtr.

*Value2*<br/>
Um número inteiro de 32 bits que pode ser convertido em um IntPtr.

*value3*<br/>
Um IntPtr.

### <a name="return-value"></a>Valor de retorno

O primeiro e o segundo operadores retornam um IntPtr. O terceiro operador retorna um ponteiro para o valor representado pelo IntPtr atual.

## <a name="toint32"> </a> Método IntPtr::ToInt32

Converte o IntPtr atual em um valor para um inteiro de 32 bits.

### <a name="syntax"></a>Sintaxe

```cpp
int32 IntPtr::ToInt32();
```

### <a name="return-value"></a>Valor de retorno

Um inteiro de 32 bits.

## <a name="see-also"></a>Consulte também

[Namespace Platform](../cppcx/platform-namespace-c-cx.md)