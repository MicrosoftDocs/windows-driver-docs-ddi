---
UID: NF:dbgmodel.IDebugHostContext2.IsEqualTo
tech.root: debugger
title: IDebugHostContext2::IsEqualTo
ms.date: 12/16/2024
targetos: Windows
description: Returns whether two IDebugHostContext objects are equal by value.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostContext2::IsEqualTo
f1_keywords:
 - IDebugHostContext2::IsEqualTo
 - dbgmodel/IDebugHostContext2::IsEqualTo
dev_langs:
 - c++
helpviewer_keywords:
 - IsEqualTo
---

## -description

Returns whether two [IDebugHostContext2](nn-dbgmodel-idebughostcontext2.md) objects are equal by value.  Note that there is no requirement for a debug host to have interface pointer equality for two contexts which are equivalent.  The actual contexts can be compared through this method.

## -parameters

### -param pContext

The host context to compare against.

### -param pIsEqual

An indication of whether the values of the two objects are equal.

## -returns

This method returns HRESULT.

## -remarks

## -see-also

[IDebugHostContext2 interface](nn-dbgmodel-idebughostcontext2.md)