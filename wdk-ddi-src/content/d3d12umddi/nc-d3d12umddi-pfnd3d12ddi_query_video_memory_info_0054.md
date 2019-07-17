---
UID: NC:d3d12umddi.PFND3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054
title: PFND3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054
author: windows-driver-content
description: Queries for video memory info.
tech.root: display
ms.assetid: 775ee197-fb24-4b5b-8be6-690759569538
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054"
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
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
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3d12umddi.h
api_name: 
 - PFND3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054
product: 
 - Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0021, 19H1
---

# PFND3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054 callback function

## -description

Queries for video memory info.

## -prototype

```
//Declaration

PFND3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054 Pfnd3d12ddiQueryVideoMemoryInfo0054; 

// Definition

void Pfnd3d12ddiQueryVideoMemoryInfo0054 
(
	D3D12DDI_HDEVICE Arg1
	UINT NodeIndex
	D3D12DDI_MEMORY_SEGMENT_GROUP_0054 MemorySegmentGroup
	D3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054 *pVideoMemoryInfo
)
{...}

```

## -parameters

### -param Arg1

[in] Handle to the device to query.

### -param NodeIndex

[in] The index of the GPU node.

### -param MemorySegmentGroup

[in] The memory segment group to query.

### -param *pVideoMemoryInfo

[out] Pointer to a D3D12DDI_QUERY_VIDEO_MEMORY_INFO_0054 structure that contains the video memory info.

## -returns

Returns void.

## -remarks


## -see-also
