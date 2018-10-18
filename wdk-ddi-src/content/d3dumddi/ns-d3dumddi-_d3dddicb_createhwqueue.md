---
UID: NS:d3dumddi._D3DDDICB_CREATEHWQUEUE
title: "_D3DDDICB_CREATEHWQUEUE"
author: windows-driver-content
description: A structure that holds information to create a hardware queue.
old-location: display\d3dddicb_createhwqueue.htm
tech.root: display
ms.assetid: 085CEF61-2C2E-4F9C-B143-2E2D58C51643
ms.date: 5/10/2018
ms.keywords: D3DDDICB_CREATEHWQUEUE, D3DDDICB_CREATEHWQUEUE structure [Display Devices], _D3DDDICB_CREATEHWQUEUE, d3dumddi/D3DDDICB_CREATEHWQUEUE, display.d3dddicb_createhwqueue
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_CREATEHWQUEUE
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_CREATEHWQUEUE
---

# _D3DDDICB_CREATEHWQUEUE structure


## -description


A structure that holds information to create a hardware queue.


## -struct-fields




### -field hHwContext

Handle to the context the queue is created for.



### -field Flags

Queue creation flags.


### -field PrivateDriverDataSize

 Size of private driver data.


### -field pPrivateDriverData

Pointer to private driver data.


### -field hHwQueue

Handle to the created queue.


### -field hHwQueueProgressFence

Handle to the hardware queue progress fence object.



### -field HwQueueProgressFenceCPUVirtualAddress

Read-only mapping of the fence value for the CPU


### -field HwQueueProgressFenceGPUVirtualAddress

Read/write mapping of the fence value for the GPU


