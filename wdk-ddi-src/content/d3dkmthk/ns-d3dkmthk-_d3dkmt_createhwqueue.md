---
UID: NS:d3dkmthk._D3DKMT_CREATEHWQUEUE
title: _D3DKMT_CREATEHWQUEUE (d3dkmthk.h)
description: Structure passed to PFND3DKMT_CREATEHWQUEUE when creating a new hardware queue.
old-location: display\d3dkmt_createhwqueue.htm
ms.assetid: DBD99353-4798-4540-89DB-EA08521B276E
ms.date: 03/24/2020
keywords: ["D3DKMT_CREATEHWQUEUE structure"]
ms.keywords: D3DKMT_CREATEHWQUEUE, D3DKMT_CREATEHWQUEUE structure [Display Devices], _D3DKMT_CREATEHWQUEUE, d3dkmthk/D3DKMT_CREATEHWQUEUE, display.d3dkmt_createhwqueue
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEHWQUEUE
f1_keywords:
 - _D3DKMT_CREATEHWQUEUE
 - d3dkmthk/_D3DKMT_CREATEHWQUEUE
 - D3DKMT_CREATEHWQUEUE
 - d3dkmthk/D3DKMT_CREATEHWQUEUE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_CREATEHWQUEUE
---

# _D3DKMT_CREATEHWQUEUE structure


## -description

Structure passed to [**PFND3DKMT_CREATEHWQUEUE**](nc-d3dkmthk-pfnd3dkmt_createhwqueue.md) when creating a new hardware queue.

## -struct-fields

### -field hHwContext

Handle to the hardware context that the queue belongs to.

### -field Flags

A bit field of [**D3DDDI_CREATEHWQUEUEFLAGS**](..\d3dukmdt\ns-d3dukmdt-_d3dddi_createhwqueueflags.md) values specifying the hardware queue creation flags.

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

## -see-also

[**D3DDDI_CREATEHWQUEUEFLAGS**](..\d3dukmdt\ns-d3dukmdt-_d3dddi_createhwqueueflags.md)

[**PFND3DKMT_CREATEHWQUEUE**](nc-d3dkmthk-pfnd3dkmt_createhwqueue.md)

