---
UID: NS:d3dkmddi._DXGKARG_SUBMITCOMMANDTOHWQUEUE
title: _DXGKARG_SUBMITCOMMANDTOHWQUEUE (d3dkmddi.h)
description: Arguments used to submit a command to the hardware queue.
ms.assetid: 914e7a49-0336-4c99-850f-95defcc4218e
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _DXGKARG_SUBMITCOMMANDTOHWQUEUE, DXGKARG_SUBMITCOMMANDTOHWQUEUE,
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARG_SUBMITCOMMANDTOHWQUEUE
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGKARG_SUBMITCOMMANDTOHWQUEUE
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARG_SUBMITCOMMANDTOHWQUEUE structure

## -description

Arguments used to submit a command to the hardware queue.

## -struct-fields

### -field hHwQueue

[in] Hardware queue being submitted to.

### -field HwQueueProgressFenceId

Hardware queue progress fence ID that will be signaled when the Present Blt is done on the GPU.

### -field DmaBufferVirtualAddress

The virtual address of the DMA buffer to be executed on the GPU.

### -field DmaBufferSize

The size of the DMA buffer to be executed on the GPU.

### -field DmaBufferPrivateDataSize

The buffer's private data size.

### -field pDmaBufferPrivateData

Binary data that is passed by the user mode DDI callback pfnSubmitToHwQueueCb, for command submissions from user mode, or for kernel mode submissions such as Present Blt, private driver data buffer filled out by DdiPresent. 

> [!Important]
> The private driver data buffer will be freed upon the return from DxgkDdiSubmitCommandToHwQueue. This is different from WDDM 2.0-2.3, where the private driver data lifetime is extended until the command buffer completion on the GPU.

### -field Flags

These will be set to zero for user mode driver generated command buffers. Kernel mode driver DdiPresentToHwQueue generated command buffers will have Present flag set to 1.

### -field HwQueueProgressFenceGpuVa

GPU VA (video acceleration) of the fence that will be signaled upon this DMA buffer completion.

### -field HwQueueProgressFenceCpuVa

Kernel mode CPU VA of the fence that will be signaled upon this DMA buffer completion.

If the node being submitted to has *RingBufferFenceRelease* cap set to 0, the fence update is inserted by the user mode driver as the last instruction at the end of the DMA buffer, or for kernel submissions, by the kernel mode driver in response to DdiSignalMonitoredFence call.

If the node being submitted to has *RingBufferFenceRelease* cap set to 1, the fence update is performed after the DMA buffer is no longer in use by either GPU or CPU. Exact mechanics of the fence update are up to the KMD/GPU. As an example, it can be done by the context management processor hardware when retiring the DMA buffer, or by the KMD.
