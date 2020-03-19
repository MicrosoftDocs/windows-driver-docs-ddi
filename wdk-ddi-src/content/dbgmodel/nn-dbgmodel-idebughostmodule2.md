---
UID: NN:dbgmodel.IDebugHostModule2
title: IDebugHostModule2 (dbgmodel.h)
description: An (IDebugHostSymbol derived) interface to a particular module.
ms.assetid: d0afd86c-b48e-46ce-8eeb-248705d7e467
ms.date: 06/11/2019
keywords: ["IDebugHostModule2 interface"]
f1_keywords:
 - "dbgmodel/IDebugHostModule2"
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
- IDebugHostModule2
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule2 interface

## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to a particular module.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance
IDebugHostModule2 interits from [IDebugHostModule](nn-dbgmodel-idebughostmodule.md). 
## -remarks

The debugger's notion of a module that is loaded within some address space is represented in two distinct ways in the data model: 

- At the type system level via the [IDebugHostModule](nn-dbgmodel-idebughostmodule.md) interface. Here, a module is a symbol and core attributes of the module are interface method calls

- Projected at the data model level via the Debugger.Models.Module data model. This is an extensible encapsulation of the type system [IDebugHostModule](nn-dbgmodel-idebughostmodule.md) representation of a module.

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
