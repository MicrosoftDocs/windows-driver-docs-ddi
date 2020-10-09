---
UID: NN:dbgmodel.IDebugHostPublic
title: IDebugHostPublic (dbgmodel.h)
description: An (IDebugHostSymbol derived) interface to a public symbol (address/name only).
ms.assetid: 18775b1d-4efc-422c-8920-21de383fb5b9
ms.date: 07/13/2018
keywords: ["IDebugHostPublic interface"]
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
 - IDebugHostPublic
 - dbgmodel/IDebugHostPublic
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostPublic
---

# IDebugHostPublic interface


## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to a public symbol (address/name only).

Represents a symbol within the publics table of a PDB. This does not have type information associated with it. It is a name and address.

## -inheritance

IDebugHostPublic interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md).

## -remarks

Public symbols represent things in the public table within a symbol file. They are, in effect, export addresses. There is no type information associated with a public symbol -- only an address. Unless a public symbol is explicitly requested by the caller, the debug host prefers to return private symbols for every inquiry. A public symbol is expressed by the IDebugHostPublic interface.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)