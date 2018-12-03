---
UID: NC:d3d12umddi.PFND3D12DDI_CLEAR_RENDER_TARGET_VIEW_0003
title: PFND3D12DDI_CLEAR_RENDER_TARGET_VIEW_0003
author: windows-driver-content
description: The pfnClearRenderTargetView function clears the specified render-target view by setting it to a constant value.
tech.root: display
ms.assetid: 8d82a8a1-13c6-4526-816d-b95c598429b3
ms.author: windowsdriverdev
ms.date: 11/28/2018
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10
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
 - PFND3D12DDI_CLEAR_RENDER_TARGET_VIEW_0003
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CLEAR_RENDER_TARGET_VIEW_0003 callback function

## -description

The pfnClearRenderTargetView function clears the specified render-target view by setting it to a constant value.

## -prototype

```
//Declaration

PFND3D12DDI_CLEAR_RENDER_TARGET_VIEW_0003 Pfnd3d12ddiClearRenderTargetView0003; 

// Definition

VOID Pfnd3d12ddiClearRenderTargetView0003 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_CPU_DESCRIPTOR_HANDLE ViewCPUHandle
	 const FLOAT[4]
	UINT NumRects
	 const D3D12DDI_RECT *pRects
)
{...}

```

## -parameters

### -param Arg1

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param ViewCPUHandle

Type: D3D12DDI_CPU_DESCRIPTOR_HANDLE

Describes the CPU descriptor handle that represents the start of the heap for the render target to clear.

### -param FLOAT[4]

A 4-component array that containing the values to fill the unordered-access-view resource with.

### -param NumRects

The number of rectangles in the array that the *pRects* parameter specifies.

### -param *pRects

An array of D3D12DDI_RECT structures for the rectangles in the render target view to clear. 

## -returns

Returns VOID.

## -remarks



## -see-also