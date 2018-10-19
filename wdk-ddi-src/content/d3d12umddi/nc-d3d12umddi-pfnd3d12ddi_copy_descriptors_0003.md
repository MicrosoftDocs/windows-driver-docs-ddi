---
UID: NC:d3d12umddi.PFND3D12DDI_COPY_DESCRIPTORS_0003
title: PFND3D12DDI_COPY_DESCRIPTORS_0003
author: windows-driver-content
description: Copy descriptors.
ms.assetid: 0409bbc2-7e61-4dd0-bfa6-6309565741e6
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
-	PFND3D12DDI_COPY_DESCRIPTORS_0003
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_COPY_DESCRIPTORS_0003 callback function

## -description

Copy descriptors.

## -prototype

```cpp
//Declaration

PFND3D12DDI_COPY_DESCRIPTORS_0003 Pfnd3d12ddiCopyDescriptors0003; 

// Definition

VOID Pfnd3d12ddiCopyDescriptors0003 
(
	 D3D12DDI_HDEVICE
	UINT NumDestDescriptorRanges
	CONST D3D12DDI_CPU_DESCRIPTOR_HANDLE *pDestDescriptorRangeStarts
	CONST UINT *pDestDescriptorRangeSizes
	UINT NumSrcDescriptorRanges
	CONST D3D12DDI_CPU_DESCRIPTOR_HANDLE *pSrcDescriptorRangeStarts
	CONST UINT *pSrcDescriptorRangeSizes
	D3D12DDI_DESCRIPTOR_HEAP_TYPE DescriptorHeapsType
)
{...}

PFND3D12DDI_COPY_DESCRIPTORS_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param NumDestDescriptorRanges

The number of descriptor ranges in the destination.

### -param *pDestDescriptorRangeStarts

Pointer to the start of the descriptor range in the destination.

### -param *pDestDescriptorRangeSizes

Pointer to the descriptor range sizes in the destination.

### -param NumSrcDescriptorRanges

The number of descriptor ranges in the source.

### -param *pSrcDescriptorRangeStarts

Pointer to the start of the descriptor range in the source.

### -param *pSrcDescriptorRangeSizes

Pointer to the descriptor range sizes in the destination.

### -param DescriptorHeapsType

The descriptor heap type.

## -returns

Returns VOID.
