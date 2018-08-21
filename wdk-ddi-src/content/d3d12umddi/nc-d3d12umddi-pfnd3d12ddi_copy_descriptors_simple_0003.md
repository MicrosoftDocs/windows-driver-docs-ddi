---
UID: NC:d3d12umddi.PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003
title: PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003
author: windows-driver-content
description: 
ms.assetid: 25baad7c-0250-45bd-8257-6d6ffc35810f
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_COPY_DESCRIPTORS_SIMPLE_0003 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
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

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param NumDescriptors: 
### -param DestDescriptorRangeStart: 
### -param SrcDescriptorRangeStart: 
### -param DescriptorHeapsType: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also