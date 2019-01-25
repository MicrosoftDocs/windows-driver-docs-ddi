---
UID: NC:d3dkmddi.DXGKDDI_PRESENTTOHWQUEUE
title: DXGKDDI_PRESENTTOHWQUEUE (d3dkmddi.h)
description: Copies content from a source allocation, given a handle to a hardware queue.
ms.assetid: af78bc41-2a61-4ba3-be19-8daa7ebc8554
ms.date: 10/19/2018
ms.topic: callback
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
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
-	d3dkmddi.h
api_name: 
-	DXGKDDI_PRESENTTOHWQUEUE
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# DXGKDDI_PRESENTTOHWQUEUE callback function

## -description

Copies content from a source allocation, given a handle to a hardware queue.

## -prototype

```cpp
//Declaration

DXGKDDI_PRESENTTOHWQUEUE DxgkddiPresenttohwqueue; 

// Definition

NTSTATUS DxgkddiPresenttohwqueue 
(
	IN_CONST_HANDLE hHwQueue
	INOUT_PDXGKARG_PRESENT pPresent
)
{...}

```

## -parameters

### -param hHwQueue

Handle to the hardware queue that the DMA buffer will be submitted to.

### -param pPresent

A pointer to a [DXGKARG_PRESENT](ns-d3dkmddi-_dxgkarg_present.md) structure that contains information about the copy operation.

## -returns

*DXGKDDI_PRESENTTOHWQUEUE* returns one of the following values:

|Return code|Description|
| -- | -- |
|STATUS_SUCCESS|Successfully copied the content.|
|STATUS_NO_MEMORY or STATUS_INSUFFICIENT_RESOURCES|Could not allocate memory that was required for it to complete.|
|STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER|The current direct memory access (DMA) buffer is depleted.|
|STATUS_GRAPHICS_CANNOTCOLORCONVERT|The display miniport driver detected a bit-block transfer (bitblt) for color conversion that the device could not perform. The Microsoft Direct3D runtime prevents the application from continuing, and the application receives a failure to copy content.|
|STATUS_PRIVILEGED_INSTRUCTION|Detected nonprivileged instructions (that is, instructions that access memory beyond the privilege of the current central processing unit [CPU] process).|
|STATUS_ILLEGAL_INSTRUCTION|Detected instructions that graphics hardware cannot support.|
|STATUS_INVALID_HANDLE|Detected an invalid handle in the command buffer.|
|STATUS_GRAPHICS_GPU_EXCEPTION_ON_DEVICE|The display miniport driver detected an error in the DMA stream. The graphics context device is placed in a lost state if the driver returns this error code.|


## -remarks

WDDM synchronization class: [Zero level](https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level)


## -see-also
