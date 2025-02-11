---
UID: NF:dbgmodel.IDebugHostFunctionLocalStorage.GetValidRange
tech.root: debugger
title: IDebugHostFunctionLocalStorage::GetValidRange
ms.date: 02/03/2025
targetos: Windows
description: The GetValidRange method retrieves a set of module-relative addresses for which this storage is valid and whether it is guaranteed within said range.
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
 - IDebugHostFunctionLocalStorage::GetValidRange
f1_keywords:
 - IDebugHostFunctionLocalStorage::GetValidRange
 - dbgmodel/IDebugHostFunctionLocalStorage::GetValidRange
dev_langs:
 - c++
helpviewer_keywords:
 - GetValidRange
---

## -description

The GetValidRange method retrieves a set of module-relative addresses for which this storage is valid and whether it is guaranteed within said range.

## -parameters

### -param start

An output pointer to a ULONG64 type that receives the start address of the valid range.

### -param end

An output pointer to a ULONG64 type that receives the end address of the valid range.

### -param guaranteed

An output pointer to a bool type that indicates whether this storage is guaranteed within the valid range.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalStorage interface](nn-dbgmodel-idebughostfunctionlocalstorage.md)