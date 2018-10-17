---
UID: NC:d3d12umddi.PFND3D12DDI_GET_DEBUG_ALLOCATION_INFO_0012
title: PFND3D12DDI_GET_DEBUG_ALLOCATION_INFO_0012
author: windows-driver-content
description: Returns the associated kernel mode allocation handles and GPU Virtual Address ranges.
ms.assetid: 335eb3b8-d6ce-4158-a710-796a504dc40d
ms.date: 
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_GET_DEBUG_ALLOCATION_INFO_0012
product:
- Windows
targetos: Windows
---

# PFND3D12DDI_GET_DEBUG_ALLOCATION_INFO_0012 callback function

## -description

Returns the associated kernel mode allocation handles and GPU Virtual Address ranges.

## -prototype

```
//Declaration

PFND3D12DDI_GET_DEBUG_ALLOCATION_INFO_0012 Pfnd3d12ddiGetDebugAllocationInfo0012; 

// Definition

VOID Pfnd3d12ddiGetDebugAllocationInfo0012 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HANDLE_AND_TYPE Object
	UINT *pNumVirtualAddressInfos
	D3D12DDI_DEBUG_VIRTUAL_ADDRESS_ALLOCATION_INFO_0012 *pVirtualAddressInfos
	UINT *pNumKMTInfos
	D3D12DDI_DEBUG_KMT_ALLOCATION_INFO_0012 *pKMTInfos
)
{...}

```

## -parameters

### -param hDevice

A handle to the device that the resource or allocation is associated with.

### -param Object

A D3D12DDI_HANDLE_AND_TYPE data type that represents a kernel-mode handle to the resource that is associated with the allocations.

### -param *pNumVirtualAddressInfos

Pointer to the number of virtual address info.

### -param *pVirtualAddressInfos

Pointer to the debug virtual address information structure.

### -param *pNumKMTInfos

Pointer to the number of kernel mode thread info.

### -param *pKMTInfos: 

Pointer to the kernel mode thread info.

## -returns

Returns VOID.

## -remarks




## -see-also
