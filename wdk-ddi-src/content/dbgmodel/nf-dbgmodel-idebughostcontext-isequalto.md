---
UID: NF:dbgmodel.IDebugHostContext.IsEqualTo
title: IDebugHostContext::IsEqualTo (dbgmodel.h)
description: Returns whether two IDebugHostContext objects are equal by value. 
ms.assetid: f0b782ca-f7b8-4521-9e2b-dd5afd5adeee
ms.date: 09/20/2018
keywords: ["IDebugHostContext::IsEqualTo"]
f1_keywords:
 - "dbgmodel/IDebugHostContext.IsEqualTo"
 - "IDebugHostContext.IsEqualTo"
ms.keywords: IDebugHostContext::IsEqualTo, IsEqualTo, IDebugHostContext.IsEqualTo, IDebugHostContext::IsEqualTo, IDebugHostContext.IsEqualTo
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
- IDebugHostContext.IsEqualTo
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostContext::IsEqualTo


## -description

Returns whether two [IDebugHostContext](nn-dbgmodel-idebughostcontext.md) objects are equal by value.  Note that there is no requirement for a debug host to have interface pointer equality for two contexts which are equivalent.  The actual contexts can be compared through this method.

## -parameters

### -param pContext
The host context to compare against.

### -param pIsEqual
An indication of whether the values of the two objects are equal.


## -returns
This method returns HRESULT.
## -remarks

## -see-also
[IDebugHostContext interface](nn-dbgmodel-idebughostcontext.md)
