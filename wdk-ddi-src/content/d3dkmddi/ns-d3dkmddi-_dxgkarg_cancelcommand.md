---
UID: NS:d3dkmddi._DXGKARG_CANCELCOMMAND
title: _DXGKARG_CANCELCOMMAND (d3dkmddi.h)
description: Specifies internal resources that are cleaned up by the DxgkDdiCancelCommand function after a command is removed from the hardware queue.
old-location: display\dxgkarg_cancelcommand.htm
ms.assetid: c0066718-50d0-4bd2-a1bf-678c3f6b9253
ms.date: 05/10/2018
keywords: ["_DXGKARG_CANCELCOMMAND structure"]
ms.keywords: DXGKARG_CANCELCOMMAND, DXGKARG_CANCELCOMMAND structure [Display Devices], _DXGKARG_CANCELCOMMAND, d3dkmddi/DXGKARG_CANCELCOMMAND, display.dxgkarg_cancelcommand
f1_keywords:
 - "d3dkmddi/DXGKARG_CANCELCOMMAND"
 - "DXGKARG_CANCELCOMMAND"
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dkmddi.h
api_name:
- DXGKARG_CANCELCOMMAND
targetos: Windows
tech.root: display
req.typenames: DXGKARG_CANCELCOMMAND
---

# _DXGKARG_CANCELCOMMAND structure


## -description


Specifies internal resources that are cleaned up by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_cancelcommand">DxgkDdiCancelCommand</a> function after a command is removed from the hardware  queue.


## -struct-fields




### -field hContext

[in] If the driver is multiple-engine aware (that is, the driver supports context creation), a handle to the device context that the cancel request originated from. 

For some paging operations, <b>hContext</b> is <b>NULL</b> (for example, paging operations that evict the content of the entire frame buffer during power management). Paging operations are indicated by the <b>Paging</b> bit-field flag in the <b>Flags</b> member.


### -field pDmaBuffer

[out] A pointer to the start of the DMA buffer, which is aligned on 4 KB.


### -field DmaBufferSize

[in] The size, in bytes, of the DMA buffer that <b>pDmaBuffer</b> points to.


### -field DmaBufferSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer that <b>pDmaBuffer</b> specifies to the start of the portion of the DMA buffer that requires canceling. The offset that is received at patch time matches the offset that is received at submission time.


### -field DmaBufferSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer that <b>pDmaBuffer</b> specifies to the end of the portion of the DMA buffer that requires canceling.


### -field pDmaBufferPrivateData

[in] A pointer to the driver-resident private data that is associated with the DMA buffer that <b>pDmaBuffer</b> points to. 


### -field DmaBufferPrivateDataSize

[in] The size, in bytes, of the private driver data at <b>pDmaBufferPrivateData</b>.

Note that <b>DmaBufferPrivateDataSize</b> represents the entire length of the private driver data buffer; however, the portion that is associated with the current cancellation request might be smaller.


### -field DmaBufferPrivateDataSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the start of the portion of the private data that is associated with the current cancellation request.


### -field DmaBufferPrivateDataSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the end of the portion of the private data that is associated with the current cancellation request.


### -field pAllocationList

[in] A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to. 


### -field AllocationListSize

[in] The number of elements in the array that <b>pAllocationList</b> specifies.

Note that <b>AllocationListSize</b> represents the total size of the allocation list; however, the portion of the allocation list that is associated with the current cancellation request might be smaller. 


### -field pPatchLocationList

[in] A pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a> structures for the list of patch locations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to.

Note that the array can begin with an element that is before the range that is used to patch the DMA buffer.


### -field PatchLocationListSize

[in] The number of elements in the array that <b>pPatchLocationList</b> specifies.

Note that <b>PatchLocationListSize</b> represents the total size of the patch-location list; however, the range that the driver must process is typically smaller. 


### -field PatchLocationListSubmissionStart

[in] The index of the first element in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed. 


### -field PatchLocationListSubmissionLength

[in] The number of elements in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed.


### -field DmaBufferVirtualAddress

 


### -field DmaBufferUmdPrivateDataSize

 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_patchlocationlist">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_cancelcommand">DxgkDdiCancelCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>
 

 

