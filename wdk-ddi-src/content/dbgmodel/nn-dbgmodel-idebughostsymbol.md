---
UID: NN:dbgmodel.IDebugHostSymbol
title: IDebugHostSymbol (dbgmodel.h)
description: An interface to a particular symbol.
ms.date: 07/13/2018
keywords: ["IDebugHostSymbol interface"]
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
 - IDebugHostSymbol
 - dbgmodel/IDebugHostSymbol
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbol
---

# IDebugHostSymbol interface


## -description

An interface to a particular symbol.

## -inheritance

IDebugHostSymbol interits from IUnknown.

## -remarks

Every symbol that can be returned from the data model host will derive in some fashion from IDebugHostSymbol. This is the core interface that every symbol implements regardless of the kind of symbol. Depending on the kind of symbol, a given symbol may implement a set of other interfaces which return attributes more unique to the particular kind of symbol represented by this interface.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
