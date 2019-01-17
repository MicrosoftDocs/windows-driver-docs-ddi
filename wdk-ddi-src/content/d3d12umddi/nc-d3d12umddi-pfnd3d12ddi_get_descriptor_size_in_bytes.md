---
UID: NC:d3d12umddi.PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES
title: PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES
description: Gets the size of the handle for a given type of descriptor heap.
ms.assetid: 3387f063-96f5-4d77-b006-924738808d51
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
-	PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES callback function

## -description

The PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES callback function gets the size of the handle, in bytes, for a given type of descriptor heap.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES Pfnd3d12ddiGetDescriptorSizeInBytes; 

// Definition

UINT Pfnd3d12ddiGetDescriptorSizeInBytes 
(
	 D3D12DDI_HDEVICE hDevice
	 D3D12DDI_DESCRIPTOR_HEAP_TYPE
)
{...}

PFND3D12DDI_GET_DESCRIPTOR_SIZE_IN_BYTES 


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param D3D12DDI_DESCRIPTOR_HEAP_TYPE

The D3D12DDI_DESCRIPTOR_HEAP_TYPE-typed value that specifies the type of descriptor heap to get the size of the handle increment for.

## -returns

Returns UINT.


## -see-also
