---
UID: NF:dbgmodel.IDebugHostFunctionLocalStorage.GetOffset
tech.root: debugger 
title: IDebugHostFunctionLocalStorage::GetOffset
ms.date: 02/03/2025
targetos: Windows
description: The GetOffset method retrieves the offset from the register where the local data is stored.
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
 - IDebugHostFunctionLocalStorage::GetOffset
f1_keywords:
 - IDebugHostFunctionLocalStorage::GetOffset
 - dbgmodel/IDebugHostFunctionLocalStorage::GetOffset
dev_langs:
 - c++
helpviewer_keywords:
 - GetOffset
---

## -description

The GetOffset method retrieves the offset from the register where the local data is stored.

## -parameters

### -param offset

An output pointer to a LONG64 type that receives the offset value.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalStorage interface](nn-dbgmodel-idebughostfunctionlocalstorage.md)