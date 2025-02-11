---
UID: NF:dbgmodel.IDebugHostFunctionLocalStorageEnumerator.GetNext
tech.root: debugger
title: IDebugHostFunctionLocalStorageEnumerator::GetNext
ms.date: 02/03/2025
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
 - IDebugHostFunctionLocalStorageEnumerator::GetNext
f1_keywords:
 - IDebugHostFunctionLocalStorageEnumerator::GetNext
 - dbgmodel/IDebugHostFunctionLocalStorageEnumerator::GetNext
dev_langs:
 - c++
helpviewer_keywords:
 - GetNext
---

## -description

The GetNext method retrieves information about the next local variable within the function. Note that this method is "scopeless", meaning that it might return two local variables with the same name as they might be in different scopes.

## -parameters

### -param storage

A pointer to a pointer variable that receives the [IDebugHostFunctionLocalStorage interface](nn-dbgmodel-idebughostfunctionlocalstorage.md) of the next local variable's details.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -see-also

[IDebugHostFunctionLocalStorageEnumerator interface](nn-dbgmodel-idebughostfunctionlocalstorageenumerator.md)