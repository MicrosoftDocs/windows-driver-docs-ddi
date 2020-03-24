---
UID: NS:d3dkmthk._D3DKMT_CREATEHWQUEUE
title: _D3DKMT_CREATEHWQUEUE (d3dkmthk.h)
description: A structure holding information to create a hardware queue.
old-location: display\d3dkmt_createhwqueue.htm
ms.assetid: DBD99353-4798-4540-89DB-EA08521B276E
ms.date: 05/10/2018
keywords: ["_D3DKMT_CREATEHWQUEUE structure"]
ms.keywords: D3DKMT_CREATEHWQUEUE, D3DKMT_CREATEHWQUEUE structure [Display Devices], _D3DKMT_CREATEHWQUEUE, d3dkmthk/D3DKMT_CREATEHWQUEUE, display.d3dkmt_createhwqueue
f1_keywords:
 - "d3dkmthk/D3DKMT_CREATEHWQUEUE"
req.header: d3dkmthk.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_CREATEHWQUEUE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEHWQUEUE
---

# _D3DKMT_CREATEHWQUEUE structure


## -description


A structure holding information to create a hardware queue.


## -struct-fields




### -field hHwContext

Handle to the hardware context the queue is associated with.



### -field Flags

Hardware queue creation flags.



### -field PrivateDriverDataSize

Size of private driver data.


### -field pPrivateDriverData

Private driver data.


### -field hHwQueue

Handle to the hardware queue object to submit work to.


### -field hHwQueueProgressFence

Handle to the monitored fence object used to monitor the queue progress.


### -field HwQueueProgressFenceCPUVirtualAddress

Read-only mapping of the queue progress fence value for the CPU.


### -field HwQueueProgressFenceGPUVirtualAddress

Read/write mapping of the queue progress fence value for the GPU.

