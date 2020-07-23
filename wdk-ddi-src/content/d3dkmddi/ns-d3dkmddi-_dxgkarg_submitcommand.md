---
UID: NS:d3dkmddi._DXGKARG_SUBMITCOMMAND
title: _DXGKARG_SUBMITCOMMAND (d3dkmddi.h)
description: The DXGKARG_SUBMITCOMMAND structure describes the direct memory access (DMA) buffer that a display miniport driver submits to the hardware command execution unit.
old-location: display\dxgkarg_submitcommand.htm
ms.assetid: f0b5c7aa-855e-419a-ac27-c9f4edefd648
ms.date: 05/10/2018
keywords: ["_DXGKARG_SUBMITCOMMAND structure"]
ms.keywords: DXGKARG_SUBMITCOMMAND, DXGKARG_SUBMITCOMMAND structure [Display Devices], DmStructs_04cbfdbf-3b43-4b70-8964-75eb9f9c4128.xml, _DXGKARG_SUBMITCOMMAND, d3dkmddi/DXGKARG_SUBMITCOMMAND, display.dxgkarg_submitcommand
f1_keywords:
 - "d3dkmddi/DXGKARG_SUBMITCOMMAND"
 - "DXGKARG_SUBMITCOMMAND"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dkmddi.h
api_name:
- DXGKARG_SUBMITCOMMAND
targetos: Windows
tech.root: display
req.typenames: DXGKARG_SUBMITCOMMAND
---

# _DXGKARG_SUBMITCOMMAND structure


## -description


The DXGKARG_SUBMITCOMMAND structure describes the direct memory access (DMA) buffer that a display miniport driver submits to the hardware command execution unit.


## -struct-fields




### -field hDevice

[in] If the driver is not multiple-engine aware (that is, the driver does not support context creation), a handle to the display device (graphics context) that the submission request originated from. A device handle is supplied to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a> function in the union that DXGKARG_SUBMITCOMMAND contains.

For some paging operations, <b>hDevice</b> is <b>NULL</b> (for example, paging operations that evict the content of the entire frame buffer during power management). Paging operations are indicated by the <b>Paging</b> bit-field flag in the <b>Flags</b> member. 


### -field hContext

[in] If the driver is multiple-engine aware (that is, the driver supports context creation), a handle to the device context that the submission request originated from. A context handle is supplied to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a> function in the union that DXGKARG_SUBMITCOMMAND contains. 

For some paging operations, <b>hContext</b> is <b>NULL</b> (for example, paging operations that evict the content of the entire frame buffer during power management). Paging operations are indicated by the <b>Paging</b> bit-field flag in the <b>Flags</b> member.


### -field DmaBufferSegmentId

[in] The identifier of the memory segment that the DMA buffer was paged in. 

The identifier can be zero if the driver indicated not to map the DMA buffer into the segment by setting the <b>DmaBufferSegmentSet</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_contextinfo">DXGK_CONTEXTINFO</a> structure to 0 in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a> function. If <b>DmaBufferSegmentId</b> is zero, the DMA buffer was allocated as a contiguous block of system memory.  


### -field DmaBufferPhysicalAddress

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address where the DMA buffer was paged in. 

If <b>DmaBufferSegmentId</b> is zero, <b>DmaBufferPhysicalAddress</b> is the physical address in system memory where the DMA buffer is located. 

If <b>DmaBufferSegmentId</b> is nonzero, <b>DmaBufferPhysicalAddress</b> is the segment physical address for the DMA buffer (that is, DXGK_SEGMENTDESCRIPTOR.BaseAddress + DmaBuffer.SegmentOffset). 

Note that <b>DmaBufferPhysicalAddress</b> always refers to the beginning of the DMA buffer even though the driver might be required to patch or submit a section of the DMA buffer that does not include the beginning of the DMA buffer (that is, if the <b>DmaBufferSubmissionStartOffset</b> member is nonzero). 


### -field DmaBufferSize

[in] The size, in bytes, of the DMA buffer.

Note that <b>DmaBufferSize</b> represents the entire length of the DMA buffer; however, the request to patch or submit might refer to only a portion of the DMA buffer. 


### -field DmaBufferSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer to the start of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time. 


### -field DmaBufferSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer to the end of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time. 


### -field pDmaBufferPrivateData

[in] A pointer to the driver-resident private data that is associated with the DMA buffer that was filled during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a> function. 

For paging operations, a single paging buffer is used for multiple independent submissions. In that scenario, the driver can indicate--by returning the appropriate private driver data pointer in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer">DxgkDdiBuildPagingBuffer</a> function--to have either a single driver private data range for all of the submissions or one for each submission. 


### -field DmaBufferPrivateDataSize

[in] The size, in byte,s of the private driver data that <b>pDmaBufferPrivateData</b> points to.

Note that <b>DmaBufferPrivateDataSize</b> represents the entire length of the private driver data buffer; however, the portion that is associated with the current submission might be smaller. 


### -field DmaBufferPrivateDataSubmissionStartOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the start of the portion of the private data that is associated with the current submission. <b>DmaBufferPrivateDataSubmissionStartOffset</b> is always zero for a nonpaging request. 


### -field DmaBufferPrivateDataSubmissionEndOffset

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the end of the portion of the private data that is associated with the current submission. 


### -field SubmissionFenceId

[in] A unique identifier that the driver can write into the fence command in the ring buffer, which is the buffer where DMA buffers are queued for the graphics processing unit (GPU) to run. For more information about these types of identifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/supplying-fence-identifiers">Supplying Fence Identifiers</a>.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for a flip operation. This member is valid only when the <b>Flip</b> or <b>FlipWithNoWait</b> bit-field flag is set in the <b>Flags</b> member. 


### -field FlipInterval

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type">D3DDDI_FLIPINTERVAL_TYPE</a>-typed value that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). <b>FlipInterval</b> is valid only if the <b>Flip</b> bit-field flag is set (that is, <b>TRUE</b>) in the <b>Flags</b> member.


### -field Flags

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_submitcommandflags">DXGK_SUBMITCOMMANDFLAGS</a> structure that identifies information about the DMA buffer to submit.


### -field EngineOrdinal

[in] Reserved for future use.


### -field DmaBufferVirtualAddress

This member is reserved and should be set to zero.

Supported starting with Windows 7.


### -field NodeOrdinal

The zero-based index of the node that the context is created for. Identifies the node when the context is <b>NULL</b>.

Supported starting with Windows 8.


## -remarks



The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a> function must be aware that multiple processes can access the device object that the <b>hDevice</b> member specifies at the same time.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_flipinterval_type">D3DDDI_FLIPINTERVAL_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_contextinfo">DXGK_CONTEXTINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_submitcommandflags">DXGK_SUBMITCOMMANDFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_interrupt">DxgkCbNotifyInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer">DxgkDdiBuildPagingBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext">DxgkDdiCreateContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_present">DxgkDdiPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a>
 

 

