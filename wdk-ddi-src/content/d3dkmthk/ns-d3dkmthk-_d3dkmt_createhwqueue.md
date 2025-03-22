---
UID: NS:d3dkmthk._D3DKMT_CREATEHWQUEUE
title: D3DKMT_CREATEHWQUEUE (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATEHWQUEUE structure.
ms.date: 03/21/2024
keywords: ["D3DKMT_CREATEHWQUEUE structure"]
req.header: d3dkmthk.h
req.construct-type: structure
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
 - _D3DKMT_CREATEHWQUEUE
 - D3DKMT_CREATEHWQUEUE
---

# D3DKMT_CREATEHWQUEUE structure (d3dkmthk.h)



## -description

**D3DKMT_CREATEHWQUEUE** is the structure passed to [**D3DKMTCreateHwQueue**](nf-d3dkmthk-d3dkmtcreatehwqueue.md) and [**PFND3DKMT_CREATEHWQUEUE**](nc-d3dkmthk-pfnd3dkmt_createhwqueue.md) when creating a new hardware queue.

## -struct-fields

### -field hHwContext

[in] Handle to the hardware context that the queue belongs to.

### -field Flags

[in] A bit field of [**D3DDDI_CREATEHWQUEUEFLAGS**](..\d3dukmdt\ns-d3dukmdt-_d3dddi_createhwqueueflags.md) values specifying the hardware queue creation flags.

### -field PrivateDriverDataSize

[in] Size of private driver data, in bytes.

### -field pPrivateDriverData

[in/out] Pointer to the private driver data.

### -field hHwQueue

[out] Handle to the created hardware queue object to submit work to.

### -field hHwQueueProgressFence

[out] Handle to the monitored fence object used to monitor the queue progress.

### -field HwQueueProgressFenceCPUVirtualAddress

[out] Read-only mapping of the queue progress fence value for the CPU.

### -field HwQueueProgressFenceGPUVirtualAddress

[out] Read/write mapping of the queue progress fence value for the GPU.

## -see-also

[**D3DDDI_CREATEHWQUEUEFLAGS**](..\d3dukmdt\ns-d3dukmdt-_d3dddi_createhwqueueflags.md)

[**PFND3DKMT_CREATEHWQUEUE**](nc-d3dkmthk-pfnd3dkmt_createhwqueue.md)

