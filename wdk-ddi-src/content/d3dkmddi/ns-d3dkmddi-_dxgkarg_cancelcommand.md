---
UID: NS:d3dkmddi._DXGKARG_CANCELCOMMAND
title: _DXGKARG_CANCELCOMMAND
author: windows-driver-content
description: Specifies internal resources that are cleaned up by the DxgkDdiCancelCommand function after a command is removed from the hardware queue.
old-location: display\dxgkarg_cancelcommand.htm
old-project: display
ms.assetid: c0066718-50d0-4bd2-a1bf-678c3f6b9253
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKARG_CANCELCOMMAND, DXGKARG_CANCELCOMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_CANCELCOMMAND
req.alt-loc: D3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGKARG_CANCELCOMMAND
---

# _DXGKARG_CANCELCOMMAND structure



## -description
Specifies internal resources that are cleaned up by the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_cancelcommand.md">DxgkDdiCancelCommand</a> function after a command is removed from the hardware  queue.



## -syntax

````
typedef struct _DXGKARG_CANCELCOMMAND {
  HANDLE                         hContext;
  VOID                           *pDmaBuffer;
  UINT                           DmaBufferSize;
  UINT                           DmaBufferSubmissionStartOffset;
  UINT                           DmaBufferSubmissionEndOffset;
  VOID                           *pDmaBufferPrivateData;
  UINT                           DmaBufferPrivateDataSize;
  UINT                           DmaBufferPrivateDataSubmissionStartOffset;
  UINT                           DmaBufferPrivateDataSubmissionEndOffset;
  const DXGK_ALLOCATIONLIST      *pAllocationList;
  UINT                           AllocationListSize;
  const D3DDDI_PATCHLOCATIONLIST *pPatchLocationList;
  UINT                           PatchLocationListSize;
  UINT                           PatchLocationListSubmissionStart;
  UINT                           PatchLocationListSubmissionLength;
} DXGKARG_CANCELCOMMAND;
````


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

[in] A pointer to an array of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to. 


### -field AllocationListSize

[in] The number of elements in the array that <b>pAllocationList</b> specifies.

Note that <b>AllocationListSize</b> represents the total size of the allocation list; however, the portion of the allocation list that is associated with the current cancellation request might be smaller. 


### -field pPatchLocationList

[in] A pointer to an array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a> structures for the list of patch locations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to.

Note that the array can begin with an element that is before the range that is used to patch the DMA buffer.


### -field PatchLocationListSize

[in] The number of elements in the array that <b>pPatchLocationList</b> specifies.

Note that <b>PatchLocationListSize</b> represents the total size of the patch-location list; however, the range that the driver must process is typically smaller. 


### -field PatchLocationListSubmissionStart

[in] The index of the first element in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed. 


### -field PatchLocationListSubmissionLength

[in] The number of elements in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_patchlocationlist.md">D3DDDI_PATCHLOCATIONLIST</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationlist.md">DXGK_ALLOCATIONLIST</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_cancelcommand.md">DxgkDdiCancelCommand</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_CANCELCOMMAND structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

