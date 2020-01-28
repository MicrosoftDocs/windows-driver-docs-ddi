---
UID: NC:d3d12umddi.PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003
title: PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003 (d3d12umddi.h)
description: Copies a descriptor.
ms.assetid: 25baad7c-0250-45bd-8257-6d6ffc35810f
ms.date: 10/19/2018
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003 callback function

## -description

Copies a descriptor.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param NumDescriptors

The number of descriptors to copy.

### -param DestDescriptorRangeStart

A handle to the descriptor range in the destination.

### -param SrcDescriptorRangeStart

A handle to the descriptor range in the source.

### -param DescriptorHeapsType

The descriptor heap type.

## -prototype

```cpp
//Declaration

PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003 Pfnd3d12ddiCopyDescriptorsSimple0003; 

// Definition

VOID Pfnd3d12ddiCopyDescriptorsSimple0003 
(
	 D3D12DDI_HDEVICE
	UINT NumDescriptors
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptorRangeStart
	D3D12DDI_CPU_DESCRIPTOR_HANDLE SrcDescriptorRangeStart
	D3D12DDI_DESCRIPTOR_HEAP_TYPE DescriptorHeapsType
)
{...}

PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003 


```

