---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetailsEnumerator.GetNext
tech.root: debugger
title: IDebugHostFunctionLocalDetailsEnumerator::GetNext
ms.date: 01/29/2025
targetos: Windows
description: The GetNext method retrieves information about the next local variable within the function. 
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
 - IDebugHostFunctionLocalDetailsEnumerator::GetNext
f1_keywords:
 - IDebugHostFunctionLocalDetailsEnumerator::GetNext
 - dbgmodel/IDebugHostFunctionLocalDetailsEnumerator::GetNext
dev_langs:
 - c++
helpviewer_keywords:
 - GetNext
---

## -description

The GetNext method retrieves information about the next local variable within the function. Note that this method is "scopeless", meaning that it might return two local variables with the same name as they might be in different scopes.

## -parameters

### -param localDetails

A pointer to a pointer variable that receives the [IDebugHostFunctionLocalDetails interface](nn-dbgmodel-idebughostfunctionlocaldetails.md) of the next local variable's details.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalDetailsEnumerator interface](nn-dbgmodel-idebughostfunctionlocaldetailsenumerator.md)