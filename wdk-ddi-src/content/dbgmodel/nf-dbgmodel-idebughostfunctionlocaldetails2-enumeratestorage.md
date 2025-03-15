---
UID: NF:dbgmodel.IDebugHostFunctionLocalDetails2.EnumerateStorage
tech.root: debugger
title: IDebugHostFunctionLocalDetails2::EnumerateStorage
ms.date: 01/29/2025
targetos: Windows
description: The EnumerateStorage method enumerates the storage for the local variable, including what registers or memory locations it may be in within the function.
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
 - IDebugHostFunctionLocalDetails2::EnumerateStorage
f1_keywords:
 - IDebugHostFunctionLocalDetails2::EnumerateStorage
 - dbgmodel/IDebugHostFunctionLocalDetails2::EnumerateStorage
dev_langs:
 - c++
helpviewer_keywords:
 - EnumerateStorage
---

## -description

The EnumerateStorage method enumerates the storage for the local variable, including what registers or memory locations it may be in within the function.

## -parameters

### -param storageEnum

A pointer to a pointer variable that receives the [IDebugHostFunctionLocalStorageEnumerator interface](nn-dbgmodel-idebughostfunctionlocalstorageenumerator.md) of the enumerated local storage locations.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalDetails2 interface](nn-dbgmodel-idebughostfunctionlocaldetails2.md)