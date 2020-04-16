---
UID: NN:dbgmodel.IDebugHostData
title: IDebugHostData (dbgmodel.h)
description: An (IDebugHostSymbol derived) interface to data.
ms.assetid: d5d3a8dd-885d-46c5-89ab-e3dc6b221654
ms.date: 07/13/2018
keywords: ["IDebugHostData interface"]
f1_keywords:
 - "dbgmodel/IDebugHostData"
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
- IDebugHostData
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostData interface

## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to data.

Represents data within a module (were this within a structure or class it would be an [IDebugHostField](nn-dbgmodel-idebughostfield.md)).


## -inheritance
IDebugHostData interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md). 
## -remarks

Data in modules which is not a member of another type is represented by the IDebugHostData interface. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
