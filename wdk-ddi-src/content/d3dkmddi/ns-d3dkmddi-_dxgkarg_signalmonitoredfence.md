---
UID: NS:d3dkmddi._DXGKARG_SIGNALMONITOREDFENCE
title: _DXGKARG_SIGNALMONITOREDFENCE (d3dkmddi.h)
description: Arguments used to add a GPU instruction to signal the paging monitored fence object to the DMA buffer.
ms.assetid: 15e5d633-9227-4ada-a7bc-91d8e1983e02
ms.date: 10/19/2018
keywords: ["DXGKARG_SIGNALMONITOREDFENCE structure"]
ms.keywords: _DXGKARG_SIGNALMONITOREDFENCE, DXGKARG_SIGNALMONITOREDFENCE, *INOUT_PDXGKARG_SIGNALMONITOREDFENCE
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARG_SIGNALMONITOREDFENCE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _DXGKARG_SIGNALMONITOREDFENCE
 - d3dkmddi/_DXGKARG_SIGNALMONITOREDFENCE
 - DXGKARG_SIGNALMONITOREDFENCE
 - d3dkmddi/DXGKARG_SIGNALMONITOREDFENCE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_SIGNALMONITOREDFENCE
dev_langs:
 - c++
---

# _DXGKARG_SIGNALMONITOREDFENCE structure


## -description

Arguments used by the [DXGKDDI_SIGNALMONITOREDFENCE](nc-d3dkmddi-dxgkddi_signalmonitoredfence.md) callback function to add a GPU instruction to signal the paging monitored fence object to the DMA buffer.

## -struct-fields

### -field KernelSubmissionType

Describes what type of kernel submission is being performed. This information can be used by the driver to choose the right synchronization class, and to ensure fence write instruction is generated in the format compatible with the buffer type being used.

### -field pDmaBuffer

A pointer to the start of the DMA buffer, which is aligned on 4 KB.

### -field DmaBufferGpuVirtualAddress

A <b>D3DGPU_VIRTUAL_ADDRESS</b> data type that indicates the virtual address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.

### -field DmaSize

The size, in bytes, of the DMA buffer that *pDmaBuffer* points to.

### -field pDmaBufferPrivateData

A pointer to a driver-resident private data structure that is used for generating the DMA buffer that *pDmaBuffer* points to.

### -field DmaBufferPrivateDataSize

The number of bytes that remain in the private data structure that *pDmaBufferPrivateData* points to for the current operation.

### -field MultipassOffset

A value that specifies the progress of the rendering operation.

### -field MonitoredFenceGpuVa

GPU VA of the monitored fence value to be updated.

### -field MonitoredFenceValue

Fence value to write from the DMA buffer being built.

### -field MonitoredFenceCpuVa

Kernel mode CPU VA of the monitored fence value to be updated.

### -field hHwQueue

 
Handle to the hardware queue that the DMA buffer will be submitted to.

## -remarks

## -see-also

