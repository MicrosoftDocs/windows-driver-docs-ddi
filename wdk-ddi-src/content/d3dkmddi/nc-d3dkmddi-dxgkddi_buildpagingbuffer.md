---
UID: NC:d3dkmddi.DXGKDDI_BUILDPAGINGBUFFER
title: DXGKDDI_BUILDPAGINGBUFFER (d3dkmddi.h)
description: The DxgkDdiBuildPagingBuffer function builds paging buffers for memory operations.
old-location: display\dxgkddibuildpagingbuffer.htm
ms.assetid: d315ff53-4a9f-46a3-ad74-d65a5eb72de1
ms.date: 05/10/2018
ms.keywords: DXGKDDI_BUILDPAGINGBUFFER, DXGKDDI_BUILDPAGINGBUFFER callback, DmFunctions_0d7a4d5b-3cd4-4c3c-9ffc-7b6e88342f81.xml, DxgkDdiBuildPagingBuffer, DxgkDdiBuildPagingBuffer callback function [Display Devices], d3dkmddi/DxgkDdiBuildPagingBuffer, display.dxgkddibuildpagingbuffer
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dkmddi.h
api_name:
- DxgkDdiBuildPagingBuffer
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_BUILDPAGINGBUFFER callback function


## -description


The <i>DxgkDdiBuildPagingBuffer</i> function builds paging buffers for memory operations.


## -parameters




### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.


### -param pBuildPagingBuffer [in]

[in/out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> structure that contains information for building a paging buffer.


## -returns



<i>DxgkDdiBuildPagingBuffer</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **STATUS_SUCCESS** | DxgkDdiBuildPagingBuffersuccessfully built a paging buffer. | 
| **STATUS_GRAPHICS_ALLOCATION_BUSY** | The GPU is currently using the allocation for the paging buffer. |
| **STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER** | More space is required in the paging buffer (that is, in the pDmaBuffer member of the [DXGKARG_BUILDPAGINGBUFFER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer) structure that the pBuildPagingBuffer parameter points to). | 


## -remarks



The <i>DxgkDdiBuildPagingBuffer</i> function is called to build special purpose direct memory access (DMA) buffers that are known as <i>paging buffers</i>. A paging buffer contains an operation that moves the content of portions of allocations:

* Within a segment of an allocation.
* Between segments of allocations.
* From a segment of an allocation to system memory.
* From system memory to a segment of an allocation.

The display miniport driver must write the appropriate graphics processing unit (GPU) instruction in the provided paging buffer (in the <b>pDmaBuffer</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a>) according to the requested paging operation; and then the driver must return the paging buffer back to the video memory manager (which is part of <i>Dxgkrnl.sys</i>). The GPU scheduler (which is also part of <i>Dxgkrnl.sys</i>) subsequently calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a> function to request that the driver submit the paging buffer as a regular DMA buffer to the GPU. 

<div class="alert"><b>Note</b>  Before the video memory manager submits the paging buffer, it calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a> function to assign (that is, <i>patch</i>) physical addresses to the paging buffer; however, in the call to <i>DxgkDdiPatch</i>, the video memory manager does not provide patch-location lists. The driver's <i>DxgkDdiPatch</i> function can perform last-minute updates to the paging buffer; however, the driver's <i>DxgkDdiPatch</i> function cannot change the size of the paging buffer.</div>
<div> </div>
When the driver successfully builds the paging buffer, the driver's <i>DxgkDdiBuildPagingBuffer</i> should update <b>pDmaBuffer</b> to point past the last byte that is written to the paging buffer and then return STATUS_SUCCESS. Because <i>DxgkDdiBuildPagingBuffer</i> can fail only if it runs out of space in the paging buffer, the driver should always verify that the paging buffer has enough space remaining before it writes to the buffer. If not enough space remains in the paging buffer, the driver should return STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER. The video memory manager would then acquire a new paging buffer and call the driver's <i>DxgkDdiBuildPagingBuffer</i> function again to fill the new paging buffer according to the requested paging operation. Note that for a given requested paging operation that fills multiple paging buffers, the scheduler calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a> function multiple times for each partial paging buffer to submit each buffer independently. 

If <i>DxgkDdiBuildPagingBuffer</i> determines that a paging operation requires more than one paging buffer, the driver can specify information in the <b>MultipassOffset</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> and can use this information across multiple iterations of the paging operation. The video memory manager initializes the information in <b>MultipassOffset</b> to zero before the first paging operation request and does not modify the information in <b>MultipassOffset</b> between iterations. Therefore, the driver can use <b>MultipassOffset</b> to save the progress between iterations. For example, the driver can store the page number that was last transferred for a paged-based transfer. 

A paging buffer is currently built for the following types of operations:

<ul>
<li>
Transfer

The transfer operation moves the content of an allocation from one location to another. This operation is the most common type of memory operation.

An allocation is always entirely transferred from one location to another. However, because of memory constraints, the transfer of an allocation can be divided into multiple sub-transfers (that is, a portion of the allocation is moved from location A to B, and then the following portion is moved, and so on, until the entire allocation is transferred). The first sub-transfer of an allocation is marked with the <b>TransferStart</b> bit-field flag in the <b>Flags</b> member of the <b>Transfer</b> member of DXGKARG_BUILDPAGINGBUFFER; the last sub-transfer of an allocation is marked with the <b>TransferEnd</b> bit-field flag. The driver is guaranteed to receive the end of a pending transfer (that is, the last sub-transfer) before the driver receives the start of a new transfer.

Each sub-transfer might require multiple calls to <i>DxgkDdiBuildPagingBuffer</i> to complete (for example, the driver might run out of DMA buffer space). Therefore, the driver might receive the <b>TransferStart</b> flag in multiple calls to <i>DxgkDdiBuildPagingBuffer</i> until the driver receives the <b>TransferEnd</b> flag in a call to <i>DxgkDdiBuildPagingBuffer</i>. Receiving the <b>TransferStart</b> flag multiple times does not indicate the start of multiple new transfers; it indicates that the sub-transfers for the allocation require multiple iterations (for example, if the driver ran out of DMA buffer space). The driver can use the <b>MultipassOffset</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> to keep track of the progress for a particular sub-transfer across multiple iterations of <i>DxgkDdiBuildPagingBuffer</i>.

Typically, a transfer occurs in a single operation. In this situation, both the <b>TransferStart</b> and <b>TransferEnd</b> bit-field flags are set.

In some scenarios, the driver might be required to set up hardware resources when certain allocations are paged in or out of memory. By default, the GPU might be using the allocation that is referenced during the call to <i>DxgkDdiBuildPagingBuffer</i>. In these scenarios, the driver might require the allocation to be idle before the driver programs the required hardware resources (that is, programming the hardware resources cannot be queued in the provided DMA buffer). For such scenarios, the driver can fail the call to <i>DxgkDdiBuildPagingBuffer</i> with STATUS_GRAPHICS_ALLOCATION_BUSY. 

If the driver returns STATUS_GRAPHICS_ALLOCATION_BUSY, the video memory manager waits until the GPU is done with any reference to the current allocation and then calls the driver's <i>DxgkDdiBuildPagingBuffer</i> function again. In the second call to <i>DxgkDdiBuildPagingBuffer</i>, the video memory manager sets the <b>AllocationIsIdle</b> bit-field flag in the <b>Flags</b> member of the <b>Transfer</b> member of DXGKARG_BUILDPAGINGBUFFER to indicate that the allocation that is being referenced is idle. If the idle flag is not set, the driver should always determine that the allocation is either currently busy or might soon become busy. If the idle flag is set, the video memory manager guarantees that the allocation that is being referenced remains idle for the duration of the call to <i>DxgkDdiBuildPagingBuffer</i>.

If the <b>hAllocation</b> member of DXGKARG_BUILDPAGINGBUFFER is <b>NULL</b>, the driver should copy the data in the source to the destination without performing any swizzling or tiling.

</li>
<li>
Fill

The fill operation fills an allocation with a specified pattern. The fill operation is used to set up the initial content of an allocation. When the content of the allocation is filled, the allocation is guaranteed to be idle (that is, not in use by the GPU). The fill operation can be performed only on a memory segment. The video memory manager never requests that the display miniport driver fill an aperture segment.

</li>
<li>
Discard content

The discard-content operation notifies the driver that an allocation is discarded from the allocation's current location in a memory segment. That is, the allocation is evicted and not copied back to system memory.

In some scenarios, the driver might be required to set up hardware resources when certain allocations are paged in or out of memory. By default, the GPU might use the allocation that is referenced during the call to <i>DxgkDdiBuildPagingBuffer</i>. In these scenarios, the driver might require the allocation to be idle before the driver programs the required hardware resources (that is, programming the hardware resources cannot be queued in the provided DMA buffer). For such scenarios, the driver can fail the call to <i>DxgkDdiBuildPagingBuffer</i> with STATUS_GRAPHICS_ALLOCATION_BUSY. 

If the driver returns STATUS_GRAPHICS_ALLOCATION_BUSY, the video memory manager waits until the GPU is done with any reference to the current allocation and then calls the driver's <i>DxgkDdiBuildPagingBuffer</i> function again. In the second call to <i>DxgkDdiBuildPagingBuffer</i>, the video memory manager sets the <b>AllocationIsIdle</b> bit-field flag in the <b>Flags</b> member of the <b>DiscardContent</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> structure to indicate that the allocation that is being referenced is idle. If the idle flag is not set, the driver should always determine that the allocation is either currently busy or might soon become busy. If the idle flag is set, the video memory manager guarantees that the allocation that is being referenced remains idle for the duration of the call to <i>DxgkDdiBuildPagingBuffer</i>.

</li>
<li>
Read physical

The read-physical operation reads from a specified physical memory address. The driver is requested to program the GPU for the operation. The size of the physical memory to access for the read can be from 1 byte through 8 bytes.  Because the data that is read is irrelevant, <i>DxgkDdiBuildPagingBuffer</i> is not required to return the data. However, in scenarios where the CPU attempts to read from AGP memory after the GPU writes to that AGP memory, the read-physical operation is critical to ensure memory coherency.

</li>
<li>
Write physical

The write-physical operation writes to a specified physical address. The driver is requested to program the GPU for the operation. The size of the physical memory to access for the write operation can be from 1 byte through 8 bytes.  Because the data that is written is irrelevant, <i>DxgkDdiBuildPagingBuffer</i> can write any data to the memory. However, in scenarios where the CPU attempts to read from AGP memory after the GPU writes to that AGP memory, the write-physical operation is critical to ensure memory coherency.

</li>
<li>
Map aperture segment

The map-aperture-segment operation maps a specified memory descriptor list (MDL) into a specified aperture segment at a specified segment offset for a specified number of pages. If the <b>CacheCoherent</b> bit-field flag is set in the <b>Flags</b> member of the <b>MapApertureSegment</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> structure, the driver must ensure that cache coherency is enforced on the pages that are mapped; otherwise, cache coherency is not required for the pages that are mapped. 

<div class="alert"><b>Note</b>  The <b>CacheCoherent</b> bit-field flag is set only when cacheable memory is being mapped into a cache-coherent aperture segment and is never set on a non-cache-coherent aperture segment or on a write-combined allocation that is mapped into a cache-coherent segment. </div>
<div> </div>
The driver can optionally use memory-mapped I/O (MMIO) to configure an aperture segment. The GPU will not be accessing the aperture range at configuration time. However, this aperture configuration must not interfere with the execution of the GPU. The GPU will not be idle when <i>DxgkDdiBuildPagingBuffer</i> is called with the DXGK_OPERATION_MAP_APERTURE_SEGMENT operation type set, and the GPU might be busy accessing other portions of the aperture segment that is being reconfigured.

</li>
<li>
Unmap aperture segment

The unmap-aperture-segment operation unmaps a previously mapped range of a specified aperture segment. The driver must map the range that is unmapped to the dummy page that the <b>DummyPage</b> member of the <b>UnmapApertureSegment</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> structure specifies. 

<div class="alert"><b>Note</b>  When the driver unmaps to the dummy page, the driver must enable GPU accesses through the specified aperture range so the DirectX graphics kernel subsystem can detect corruption issues. Conformance tests exist to check this situation. </div>
<div> </div>
The video memory manager uses the dummy page that is in the unmapped portion of the aperture to determine difficulties the memory manager has accessing the aperture segment.

The driver can optionally use MMIO to configure an aperture segment. The GPU will not be accessing the aperture range at configuration time. However, this aperture configuration must not interfere with the execution of the GPU. The GPU will not be idle when <i>DxgkDdiBuildPagingBuffer</i> is called with the DXGK_OPERATION_UNMAP_APERTURE_SEGMENT operation type set, and the GPU might be busy accessing other portions of the aperture segment that is being reconfigured.

</li>
<li>
Special-lock transfer

The special-lock-transfer operation is similar to the regular transfer operation. However, instead of transferring the content of the allocation from or to the allocation's regular backing store, the special-lock-transfer operation transfers the content of the allocation from or to the alternate virtual address that was set up for the allocation when the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a> function was called with the <b>UseAlternateVA</b> bit-field flag set. 

The special-lock-transfer operation occurs only in one of the following scenarios:

<ul>
<li>The allocation is currently CPU-accessible with an alternate virtual address and is being evicted.</li>
<li>An allocation that was previously evicted, such as the situation that is described in the preceding bullet, is being paged back in.</li>
</ul>
Drivers that do not support the use of the <b>UseAlternateVA</b> bit-field flag will not be called to perform a special-lock-transfer operation.

In some scenarios, the driver might be required to set up hardware resources when certain allocations are paged in or out of memory. By default, the GPU might be using the allocation that is referenced during the call to <i>DxgkDdiBuildPagingBuffer</i>. In these scenarios, the driver might require the allocation to be idle before the driver programs the required hardware resources (that is, programming the hardware resources cannot be queued in the provided DMA buffer). For such scenarios, the driver can fail the call to <i>DxgkDdiBuildPagingBuffer</i> with STATUS_GRAPHICS_ALLOCATION_BUSY. 

If the driver returns STATUS_GRAPHICS_ALLOCATION_BUSY, the video memory manager waits until the GPU is done with any reference to the current allocation and then calls the driver's <i>DxgkDdiBuildPagingBuffer</i> function again. In the second call to <i>DxgkDdiBuildPagingBuffer</i>, the video memory manager sets the <b>AllocationIsIdle</b> bit-field flag in the <b>Flags</b> member of the <b>SpecialLockTransfer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> structure to indicate that the allocation that is being referenced is idle. If the idle flag is not set, the driver should always determine that the allocation is either currently busy or might soon become busy. If the idle flag is set, the video memory manager guarantees that the allocation that is being referenced remains idle for the duration of the call to <i>DxgkDdiBuildPagingBuffer</i>.

</li>
</ul>
Note that if the driver must use a hardware aperture to linearize a swizzled allocation that an application can directly access, the driver must unswizzle that allocation while the driver transfers the allocation to system memory to maintain the coherency of the allocation's virtual address. The driver must unswizzle the allocation because an eviction might occur while the application is accessing the allocation. 

The system's memory manager ensures that the transfer is invisible to the application. However, because the allocation is in system memory and the allocation's virtual address can no longer go through the hardware aperture, the driver must ensure the byte ordering into system memory matches what was visible through the aperture. 

<i>DxgkDdiBuildPagingBuffer</i> should be made pageable.


#### Examples

The following code example shows how to use <i>DxgkDdiBuildPagingBuffer</i>.

```cpp
NTSTATUS ntStatus;
DXGKARG_BUILDPAGINGBUFFER param;

// The driver receives the following paging operation to build:
//
param.Flags = 0;
param.pDmaBuffer= CurrentPagingBuffer;
param.DmaSize = CurrentPagingBufferSizeLeft;
param.pDmaBufferPrivateData = CurrentPagingBufferPrivateData; 
param.DmaBufferPrivateDataSize = CurrentPagingBufferPrivateDataSizeLeft; 
param.Operation = DXGK_OPERATION_TRANSFER; 
param.Transfer.Flags = 0; 
param.Transfer.TransferOffset = CurrentOffsetInAllocationBeingTransfered; 
param.Transfer.hAllocation = DriverContextForAllocationBeingMoved; 
param.Transfer.Source.SegmentId = 0; // Source is an MDL. 
param.Transfer.Source.pMdl = MDLDescribingPagesForAllocationBeingMoved; 
param.Transfer.Destination.SegmentId = 1; // Source to segment #1. 
param.Transfer.Destination.SegmentAddress = 0; // Source to offset 0 of segment #1.

// The driver receives MultipassOffset when it is initialized to zero 
// and uses it for multiple iterations of the paging operation.
//
param.MultipassOffset = 0;

do {
    // Call the driver's BuildPagingBuffer function to build a paging buffer.
    //
    ntStatus = BuildPagingBuffer(hAdapter, &param);
    // BuildPagingBuffer updates the size that is left in the 
    //  paging buffer with the amount of bytes that were written.
    //
    if (NT_SUCCESS(ntStatus)) {
        //
        // If STATUS_SUCCESS, batch the paging buffer to the 
        // scheduler after multiple paging operations are batched.
    }
    else if (ntStatus == STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER) {

        //
        // If STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER, submit the current paging buffer to the scheduler to let 
        // the GPU start working on a partial transfer.
 
        VidSchSubmitPagingBuffer(CurrentPagingBuffer, CurrentPagingBufferSizeLeft);
 
        // Acquire a new paging buffer to complete the transfer.
        //
        VidMmAcquirePagingBuffer(&CurrentPagingBuffer, &CurrentPagingBufferSizeLeft);
    }
    else {
        //
        // A critical failure occurred, so bugcheck the system. 
        // This situation should never occur because the driver can 
        // fail the call only if it requires more DMA buffer space.
    }
} while(!NT_SUCCESS(ntStatus))
```




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_patch">DxgkDdiPatch</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb">pfnLockCb</a>
 

 

