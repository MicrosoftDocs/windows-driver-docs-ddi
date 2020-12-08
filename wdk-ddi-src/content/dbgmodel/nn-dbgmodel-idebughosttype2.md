---
UID: NN:dbgmodel.IDebugHostType2
title: IDebugHostType2 (dbgmodel.h)
description: An (IDebugHostSymbol derived) interface to a particular type.
ms.date: 06/11/2019
keywords: ["IDebugHostType2 interface"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostType2
 - dbgmodel/IDebugHostType2
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2
---

# IDebugHostType2 interface


## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to a particular type.

A given language/native type is described by the IDebugHostType2 or [IDebugHostType](nn-dbgmodel-idebughosttype.md) interfaces. Note that some of the methods on these interfaces only apply for specific kinds of types.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance

IDebugHostType2 interits from [IDebugHostType](nn-dbgmodel-idebughosttype.md).

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
