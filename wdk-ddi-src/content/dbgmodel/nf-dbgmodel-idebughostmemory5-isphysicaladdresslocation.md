---
UID: NF:dbgmodel.IDebugHostMemory5.IsPhysicalAddressLocation
tech.root: debugger
title: IDebugHostMemory5::IsPhysicalAddressLocation
ms.date: 02/24/2025
targetos: Windows
description: The IsPhysicalAddressLocation method returns whether a given location represents a physical address or not.
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
 - IDebugHostMemory5::IsPhysicalAddressLocation
f1_keywords:
 - IDebugHostMemory5::IsPhysicalAddressLocation
 - dbgmodel/IDebugHostMemory5::IsPhysicalAddressLocation
dev_langs:
 - c++
helpviewer_keywords:
 - IsPhysicalAddressLocation
---

## -description

The IsPhysicalAddressLocation method is used to determine whether a given location represents a physical address or not.

## -parameters

### -param pLocation

A pointer to the location structure which needs to be checked.

## -returns

The function returns a boolean value. If the passed location structure represents a physical address, it returns true. Otherwise, it returns false.

## -remarks

## -see-also

[IDebugHostMemory5 interface](nn-dbgmodel-idebughostmemory5.md)