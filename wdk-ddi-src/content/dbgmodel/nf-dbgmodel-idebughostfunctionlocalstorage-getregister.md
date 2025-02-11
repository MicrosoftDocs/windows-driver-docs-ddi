---
UID: NF:dbgmodel.IDebugHostFunctionLocalStorage.GetRegister
tech.root: debugger
title: IDebugHostFunctionLocalStorage::GetRegister
ms.date: 02/03/2025
targetos: Windows
description: The GetRegister method retrieves the register the local data is stored within, or the register it is relative to. The returned value is architecture-specific.
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
 - IDebugHostFunctionLocalStorage::GetRegister
f1_keywords:
 - IDebugHostFunctionLocalStorage::GetRegister
 - dbgmodel/IDebugHostFunctionLocalStorage::GetRegister
dev_langs:
 - c++
helpviewer_keywords:
 - GetRegister
---

## -description

The GetRegister method retrieves the register the local data is stored within, or the register it is relative to. The returned value is architecture-specific.

## -parameters

### -param registerId

An output pointer to a ULONG type that receives the architecture-specific register ID where the local is stored.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalStorage interface](nn-dbgmodel-idebughostfunctionlocalstorage.md)