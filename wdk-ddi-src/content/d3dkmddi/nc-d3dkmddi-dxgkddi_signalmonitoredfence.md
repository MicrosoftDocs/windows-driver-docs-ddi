---
UID: NC:d3dkmddi.DXGKDDI_SIGNALMONITOREDFENCE
title: DXGKDDI_SIGNALMONITOREDFENCE
author: windows-driver-content
description: Adds a GPU instruction to signal the paging monitored fence object to the DMA buffer.
ms.assetid: d69e18f4-9323-4be5-ad35-3fd009c66b34
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
-	DXGKDDI_SIGNALMONITOREDFENCE
product:
-	Windows
targetos: Windows
tech.root: display
---

# DXGKDDI_SIGNALMONITOREDFENCE callback function

## -description

Adds a GPU instruction to signal the paging monitored fence object to the DMA (direct memory access) buffer. This callback function is called from a Video memory management worker thread when submitting paging buffers, and from the application thread performing kernel submissions such as [PresentBlt](../d3dumddi/nc-d3dumddi-pfnd3dddi_submitpresentblttohwqueuecb.md) or [RenderGdi](nc-d3dkmddi-dxgkddi_rendergdi.md). The OS passes a hint to the driver regarding the kernel submission type.

## -prototype

```
//Declaration

DXGKDDI_SIGNALMONITOREDFENCE DxgkddiSignalmonitoredfence; 

// Definition

NTSTATUS DxgkddiSignalmonitoredfence 
(
	IN_CONST_HANDLE hContext
	INOUT_PDXGKARG_SIGNALMONITOREDFENCE pSignalMonitoredFence
)
{...}

```

## -parameters

### -param hContext

Driver context handle for the context that generated the kernel submission.

### -param pSignalMonitoredFence: 

Pointer to a [DXGKARG_SIGNALMONITOREDFENCE](ns-d3dkmddi-_dxgkarg_signalmonitoredfence.md) structure that contains parameters to signal the monitored fence object.

## -returns

Returns NTSTATUS.

## -remarks

WDDM synchronization class: 

* [Zero Level](https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level) for RenderGdi and PresentBlt submission types.
* [First Level GPU Scheduler Class](https://docs.microsoft.com/en-us/windows-hardware/drivers/display/gpu-scheduler-class) for [BuildPagingBuffer](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) submission type.



## -see-also