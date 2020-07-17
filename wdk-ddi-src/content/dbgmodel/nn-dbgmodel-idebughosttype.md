---
UID: NN:dbgmodel.IDebugHostType
title: IDebugHostType (dbgmodel.h)
description: An (IDebugHostSymbol derived) interface to a particular type.
ms.assetid: f4fb5043-a364-45f6-9d87-43850ac0f140
ms.date: 07/13/2018
keywords: ["IDebugHostType interface"]
f1_keywords:
 - "dbgmodel/IDebugHostType"
 - "IDebugHostType"
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType interface

## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to a particular type.

A given language/native type is described by the [IDebugHostType2](nn-dbgmodel-idebughosttype2.md) or IDebugHostType interfaces. Note that some of the methods on these interfaces only apply for specific kinds of types.


## -inheritance
IDebugHostType interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md). 
## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
