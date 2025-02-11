---
UID: NF:dbgmodel.IDebugHostFunctionLocalStorage2.GetExtendedRegisterAddressInfo
tech.root: debugger
title: IDebugHostFunctionLocalStorage2::GetExtendedRegisterAddressInfo
ms.date: 02/03/2025
targetos: Windows
description: The GetExtendedRegisterAddressInfo method retrieves the architecture-specific register address information in which local data is stored.
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
 - IDebugHostFunctionLocalStorage2::GetExtendedRegisterAddressInfo
f1_keywords:
 - IDebugHostFunctionLocalStorage2::GetExtendedRegisterAddressInfo
 - dbgmodel/IDebugHostFunctionLocalStorage2::GetExtendedRegisterAddressInfo
dev_langs:
 - c++
helpviewer_keywords:
 - GetExtendedRegisterAddressInfo
---

## -description

The GetExtendedRegisterAddressInfo method retrieves the architecture-specific register address information in which local data is stored. The information includes the register ID, the offset, whether the access is indirect, and the indirect offset if applicable.

## -parameters

### -param registerId

An output pointer to a ULONG type that will receive the ID of the register where the local is stored.

### -param offset

An output pointer to a LONG64 type that receives the offset from the register.

### -param isIndirectAccess

An output pointer to a bool type that indicates whether the access to this storage is indirect.

### -param indirectOffset

An output pointer to a LONG type that receives the offset if the access is indirect.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostFunctionLocalStorage2 interface](nn-dbgmodel-idebughostfunctionlocalstorage2.md)