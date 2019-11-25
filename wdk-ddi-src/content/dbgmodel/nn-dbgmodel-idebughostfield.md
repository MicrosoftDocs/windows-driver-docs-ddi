---
UID: NN:dbgmodel.IDebugHostField
title: IDebugHostField (dbgmodel.h)
description: Represents a field within a structure or class.
ms.assetid: e3b8dddc-1481-41ad-b162-4f5162aed653
ms.date: 07/13/2018
ms.topic: interface
f1_keywords:
 - "dbgmodel/IDebugHostField"
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
- IDebugHostField
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostField interface

## -description

Represents a field within a structure or class.


## -inheritance
IDebugHostField interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md). 
## -remarks

The IDebugHostField class represents a symbol which is a data member of a class, structure, union, or other type construct. It does not represent free data (e.g.: global data). 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
