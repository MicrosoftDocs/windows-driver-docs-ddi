---
UID: NF:dbgmodel.IDebugHostMemory5.GetPhysicalAddressLocation
tech.root: debugger
title: IDebugHostMemory5::GetPhysicalAddressLocation
ms.date: 02/24/2025
targetos: Windows
description: The GetPhysicalAddressLocation method creates a location structure that represents an offset as a physical memory address.
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
 - IDebugHostMemory5::GetPhysicalAddressLocation
f1_keywords:
 - IDebugHostMemory5::GetPhysicalAddressLocation
 - dbgmodel/IDebugHostMemory5::GetPhysicalAddressLocation
dev_langs:
 - c++
helpviewer_keywords:
 - GetPhysicalAddressLocation
---

## -description

The GetPhysicalAddressLocation method creates a location structure that represents an offset as a physical memory address. Failure is a legitimate outcome (E_NOTIMPL) if the debugger does not support physical addressing. However, if the debugger supports physical addressing but a particular target does not, GetPhysicalAddressLocation will succeed but read attempts from that location will fail.

On successful execution of this method, the resulting location can be utilized with any method that requires a location. This includes the creation of typed objects at a physical address. Callers are free to modify the offset of the returned location after the method successfully returns.

## -parameters

### -param physAddr

The physical memory address which needs to be represented as location structure.

### -param pPhysicalAddressLocation

A pointer to the storage location where the location structure representing the physical memory address will be stored.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

If this method succeeds, the location can be utilized with any method that takes a location (including the creation of typed objects at a physical address).

## -see-also

[IDebugHostMemory5 interface](nn-dbgmodel-idebughostmemory5.md)