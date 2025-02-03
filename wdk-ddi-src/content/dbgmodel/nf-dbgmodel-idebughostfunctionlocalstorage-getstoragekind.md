---
UID: NF:dbgmodel.IDebugHostFunctionLocalStorage.GetStorageKind
tech.root: debugger
title: IDebugHostFunctionLocalStorage::GetStorageKind
ms.date: 02/03/2025
targetos: Windows
description: The GetStorageKind method retrieves the storage kind of the local data.
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
 - IDebugHostFunctionLocalStorage::GetStorageKind
f1_keywords:
 - IDebugHostFunctionLocalStorage::GetStorageKind
 - dbgmodel/IDebugHostFunctionLocalStorage::GetStorageKind
dev_langs:
 - c++
helpviewer_keywords:
 - GetStorageKind
---

## -description

The GetStorageKind method retrieves the storage kind of the local data.

## -parameters

### -param kind

An output pointer to a StorageKind type that receives the kind of local storage.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalStorage interface](nn-dbgmodel-idebughostfunctionlocalstorage.md)