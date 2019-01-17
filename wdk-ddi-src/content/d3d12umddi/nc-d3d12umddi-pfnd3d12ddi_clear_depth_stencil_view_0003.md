---
UID: NC:d3d12umddi.PFND3D12DDI_CLEAR_DEPTH_STENCIL_VIEW_0003
title: PFND3D12DDI_CLEAR_DEPTH_STENCIL_VIEW_0003
description: The pfnClearDepthStencilView function clears the specified currently bound depth-stencil view.
tech.root: display
ms.assetid: f927db61-5d0c-4e5b-a3c1-811e2acf7f4d
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
 - PFND3D12DDI_CLEAR_DEPTH_STENCIL_VIEW_0003
product: 
 - Windows
targetos: Windows
---

# PFND3D12DDI_CLEAR_DEPTH_STENCIL_VIEW_0003 callback function

## -description

The pfnClearDepthStencilView function clears the specified currently bound depth-stencil view. 

## -prototype

```
//Declaration

PFND3D12DDI_CLEAR_DEPTH_STENCIL_VIEW_0003 Pfnd3d12ddiClearDepthStencilView0003; 

// Definition

VOID Pfnd3d12ddiClearDepthStencilView0003 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_CPU_DESCRIPTOR_HANDLE ViewCPUHandle
	UINT Arg2
	FLOAT Arg3
	UINT8 Arg4
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

Describes the CPU descriptor handle that represents the start of the heap for the depth stencil view to clear.

### -param Arg2

A value that specifies which parts of the buffer to affect. 

### -param Arg3

A single-precision float vector to set the depth to. 

### -param Arg4

An unsigned 8-bit integer value to set the stencil to.

### -param NumRects

The number of rectangles in the array that the *pRects* parameter specifies.

### -param *pRects

An array of D3D12DDI_RECT structures for the rectangles in the resource view to clear. 

## -returns

Returns VOID.

## -remarks



## -see-also
