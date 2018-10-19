---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO
title: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO
author: windows-driver-content
description: The pfnCheckExistingResourceAllocationInfo callback function supports checking existing resource allocation information.
ms.assetid: d93b90b4-3509-42bf-8ec2-2fc0bd47b2f9
ms.date: 10/19/2018
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
-	PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO callback function

## -description

The pfnCheckExistingResourceAllocationInfo callback function supports checking existing resource allocation information. 

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO Pfnd3d12ddiCheckexisitingresourceallocationinfo; 

// Definition

VOID Pfnd3d12ddiCheckexisitingresourceallocationinfo 
(
	 D3D12DDI_HDEVICE
	 D3D12DDI_HRESOURCE
	D3D12DDI_RESOURCE_ALLOCATION_INFO *
	D3DKMT_HANDLE *phAllocation
)
{...}

PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param D3D12DDI_HRESOURCE

A handle to the device resource.

### -param *

Pointer to a D3D12DDI_RESOURCE_ALLOCATION_INFO.

### -param *phAllocation: 

Pointer to an array of handles.

## -returns

Returns VOID.
