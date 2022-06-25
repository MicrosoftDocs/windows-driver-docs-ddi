---
UID: NS:d3dkmddi._DXGKARG_BUILDPAGINGBUFFER
title: DXGKARG_BUILDPAGINGBUFFER (d3dkmddi.h)
description: The DXGKARG_BUILDPAGINGBUFFER structure describes parameters for building a paging buffer that is used in a memory-transfer operation.
old-location: display\dxgkarg_buildpagingbuffer.htm
ms.date: 06/24/2022
keywords: ["DXGKARG_BUILDPAGINGBUFFER structure"]
ms.keywords: "*IN_PDXGKARG_BUILDPAGINGBUFFER, DXGKARG_BUILDPAGINGBUFFER, DXGKARG_BUILDPAGINGBUFFER structure [Display Devices], DXGKARG_BUILDPAGINGBUFFER_OPERATION, DXGK_BUILDPAGINGBUFFER_OPERATION, DmStructs_06cb7ec2-482d-41ba-b550-3c4f27d36070.xml, _DXGKARG_BUILDPAGINGBUFFER, d3dkmddi/DXGKARG_BUILDPAGINGBUFFER, display.dxgkarg_buildpagingbuffer"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
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
req.typenames: DXGKARG_BUILDPAGINGBUFFER
f1_keywords:
 - _DXGKARG_BUILDPAGINGBUFFER
 - d3dkmddi/_DXGKARG_BUILDPAGINGBUFFER
 - DXGKARG_BUILDPAGINGBUFFER
 - d3dkmddi/DXGKARG_BUILDPAGINGBUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_BUILDPAGINGBUFFER
 - DXGKARG_BUILDPAGINGBUFFER
---

# DXGKARG_BUILDPAGINGBUFFER structure

## -description

The **DXGKARG_BUILDPAGINGBUFFER** structure describes parameters for the [DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) callback that builds a paging buffer for use in a memory-transfer operation.

## -struct-fields

### -field pDmaBuffer [in/out]

A virtual address to the first available byte in the paging buffer. When the driver is first called with a new paging buffer, this virtual address is aligned on 4 KB. The driver tightly packs operations in the paging buffer until the paging buffer is full and then uses a new paging buffer. Therefore, if the graphics processing unit (GPU) requires a specific alignment for a paging-buffer submission, the driver should enforce this alignment by padding the operations that it writes to the paging buffer. Before the [**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) function returns, the driver should update **pDmaBuffer** to point past the last byte that is written to the paging buffer.

### -field DmaSize [in/out]

The size, in bytes, of the paging buffer that **pDmaBuffer** specifies.

### -field pDmaBufferPrivateData [in/out]

A pointer to a driver-resident private data structure that is associated with the direct memory access (DMA) buffer (that is, paging buffer) that **pDmaBuffer** specifies.

### -field DmaBufferPrivateDataSize [in/out]

The number of bytes that remain in the private data structure that **pDmaBufferPrivateData** points to for the current operation.

### -field Operation [in]

A [**DXGK_BUILDPAGINGBUFFER_OPERATION**](ne-d3dkmddi-_dxgk_buildpagingbuffer_operation.md)-typed value that indicates the type of memory operation to perform.

### -field MultipassOffset [in/out]

A UINT value that specifies the progress of the paging operation if multiple paging buffers are required. The driver sets this value to indicate a split into multiple paging buffers for more than one transfer operation. For example, the driver can store the page number that was last transferred for a paged-based transfer.

### -field Transfer [in]

A structure that describes the transfer operation.

### -field Transfer.hAllocation [in]

A handle to the allocation that the driver's [**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md) function previously returned in the **hAllocation** member of a [**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md) structure, which is part of the [**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md) structure's **pAllocationInfo** member. The allocation handle points to a buffer that contains private driver data for the transfer.

### -field Transfer.TransferOffset [in]

The offset, in bytes, of the first page within the allocation that is transferred. This offset is applied only to a location that a segment location describes. This offset does not apply to an [**MDL**](../wdm/ns-wdm-_mdl.md) description of a memory range. If the driver requires more than one paging buffer to complete the transfer (that is, the driver returns STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER from its [**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) function), **TransferOffset** is the same for each call to **DxgkDdiBuildPagingBuffer** for this transfer.

### -field Transfer.TransferSize [in]

The size, in bytes, of the memory information to transfer.

### -field Transfer.Source [in]

A structure that describes the source allocation. This structure contains a **SegmentId** member and a union that contains either an offset into a segment of the source allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the source (**pMdl**).

### -field Transfer.Source.SegmentId [in]

The identifier of a segment within the source allocation, or zero if the source allocation is described by the **pMdl** member of the union that **Source** contains.

### -field Transfer.Source.SegmentAddress [in]

The source segment address, if the **SegmentId** member of **Source** is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: ```SegmentAddress = SegmentOffset + Segment.BaseAddr```.

### -field Transfer.Source.pMdl [in]

A pointer to a buffer that contains the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that describes the system memory pages for the source, if the **SegmentId** member of **Source** is zero.

### -field Transfer.Destination [in]

A structure that describes the destination allocation. This structure contains a **SegmentId** member and a union that contains either an offset into a segment of the destination allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the destination (**pMdl**).

### -field Transfer.Destination.SegmentId [in]

The identifier of a segment within the destination allocation, or zero if the destination allocation is described by the **pMdl** member of the union that **Destination** contains.

### -field Transfer.Destination.SegmentAddress [in]

The destination segment address, if the **SegmentId** member of **Destination** is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: ```SegmentAddress = SegmentOffset + Segment.BaseAddr```.

### -field Transfer.Destination.pMdl [in]

A pointer to a buffer that contains the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that describes the system memory pages for the destination, if the **SegmentId** member of **Destination** is zero.

### -field Transfer.Flags [in]

A [**DXGK_TRANSFERFLAGS**](ns-d3dkmddi-_dxgk_transferflags.md) structure that identifies, in bit-field flags, the type of special-lock-transfer operation to perform.

### -field Transfer.MdlOffset [in]

The offset, in system memory pages, within the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that the **pMdl** member points to, to the first system memory page for the current operation. The driver can obtain the physical address of the first system memory page by calling the [**MmGetMdlPfnArray**](/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetmdlpfnarray function as follows.

```cpp
MmGetMdlPfnArray(pMdl)[MdlOffset];
```

### -field Fill [in]

A structure that describes the fill operation.

### -field Fill.hAllocation [in]

A handle to the allocation that contains content to fill.

### -field Fill.FillSize [in]

The size, in bytes, of the memory information to fill.

### -field Fill.FillPattern [in]

The pattern to fill the destination with. The video memory manager uses this information to initialize video memory to a specific pattern when an allocation without content is first paged in. In this case, no source exists for the fill request—only a destination exists.

### -field Fill.Destination [in]

A structure that describes the destination allocation for the fill operation.

### -field Fill.Destination.SegmentId [in]

The identifier of a segment within the destination allocation.

### -field Fill.Destination.SegmentAddress [in]

The destination segment address. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: ```SegmentAddress = SegmentOffset + Segment.BaseAddr```.

### -field DiscardContent [in]

A structure that describes the discard-content operation.

### -field DiscardContent.hAllocation [in]

A handle to the allocation that contains content to discard.

### -field DiscardContent.Flags [in]

A [**DXGK_DISCARDCONTENTFLAGS**](ns-d3dkmddi-_dxgk_discardcontentflags.md) structure that identifies, in bit-field flags, the type of discard-content operation to perform.

### -field DiscardContent.SegmentId [in]

The identifier of a segment within the allocation to discard content from.

### -field DiscardContent.SegmentAddress [in]

A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the segment address. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: ```SegmentAddress = SegmentOffset + Segment.BaseAddr```. This location is where content is discarded from.

### -field ReadPhysical [in]

A structure that describes the read-physical operation.

### -field ReadPhysical.SegmentId [in]

The identifier of a segment that data is read from.

### -field ReadPhysical.PhysicalAddress [in]

A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address, within the segment that **SegmentId** specifies, where the data is read.

### -field WritePhysical [in]

A structure that describes the write-physical operation.

### -field WritePhysical.SegmentId [in]

The identifier of a segment to which data is written.

### -field WritePhysical.PhysicalAddress [in]

A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address, within the segment that **SegmentId** specifies, where the data is written.

### -field MapApertureSegment [in]

A structure that describes the map-aperture-segment operation using an MDL.

### -field MapApertureSegment.hDevice [in]

A handle to the device that owns the allocation that **hAllocation** specifies that is mapped into the aperture segment that **SegmentId** specifies.

For a shared allocation, **hDevice** is set to the device that the video memory manager determined to be the owner of the allocation.

**hDevice** is **NULL** for the primary allocation.

### -field MapApertureSegment.hAllocation [in]

A handle to the allocation that is mapped into the aperture segment that **SegmentId** specifies.

**hAllocation** is **NULL** when a DMA buffer is mapped into the aperture segment because DMA buffers are not explicitly created by the driver.

### -field MapApertureSegment.SegmentId [in]

The identifier of an aperture segment to configure.

### -field MapApertureSegment.OffsetInPages [in]

The offset, in pages, from the beginning of the segment to the first pages to map.

### -field MapApertureSegment.NumberOfPages [in]

The number of pages to map.

### -field MapApertureSegment.pMdl [in]

A pointer to a buffer that contains the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that describes the physical system memory pages to map into the aperture segment.

### -field MapApertureSegment.Flags [in]

A [**DXGK_MAPAPERTUREFLAGS**](ns-d3dkmddi-_dxgk_mapapertureflags.md) structure that identifies, in bit-field flags, the type of map-aperture-segment operation to perform.

### -field MapApertureSegment.MdlOffset [in]

The offset, in system memory pages, within the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that the **pMdl** member points to, to the first system memory page for the current operation. The driver can obtain the physical address of the first system memory page by calling the [**MmGetMdlPfnArray**](/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetmdlpfnarray function as follows.

```cpp
MmGetMdlPfnArray(pMdl)[MdlOffset];
```

### -field UnmapApertureSegment [in]

A structure that describes the unmap-aperture-segment operation.

### -field UnmapApertureSegment.hDevice [in]

A handle to the device that owns the allocation that **hAllocation** specifies that is unmapped from the aperture segment that **SegmentId** specifies.

For a shared allocation, **hDevice** is set to the device that the video memory manager determined to be the owner of the allocation.

**hDevice** is **NULL** for the primary allocation.

### -field UnmapApertureSegment.hAllocation [in]

A handle to the allocation that is unmapped from the aperture segment that **SegmentId** specifies.

**hAllocation** is **NULL** when a DMA buffer is unmapped from the aperture segment because DMA buffers are not explicitly created by the driver.

### -field UnmapApertureSegment.SegmentId [in]

The identifier of an aperture segment to configure.

### -field UnmapApertureSegment.OffsetInPages [in]

The offset, in pages, from the beginning of the segment to the first pages to unmap.

### -field UnmapApertureSegment.NumberOfPages [in]

The number of pages to unmap.

### -field UnmapApertureSegment.DummyPage [in]

A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address of the placeholder page where the driver should map the range that is unmapped.

### -field SpecialLockTransfer [in]

A structure that describes the special-lock-transfer operation.

### -field SpecialLockTransfer.hAllocation [in]

A handle to the allocation that the driver's [**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md) function previously returned in the **hAllocation** member of a [**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md) structure, which is part of the [**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md) structure's **pAllocationInfo** member. The allocation handle points to a buffer that contains private driver data for the special-lock transfer.

### -field SpecialLockTransfer.TransferOffset [in]

The offset, in bytes, of the first page within the allocation that is transferred. This offset is applied only to a location that a segment location describes. This offset does not apply to an [**MDL**](../wdm/ns-wdm-_mdl.md) description of a memory range. If the driver requires more than one paging buffer to complete the transfer (that is, the driver returns STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER from its [**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) function), **TransferOffset** is the same for each call to **DxgkDdiBuildPagingBuffer** for this transfer.

### -field SpecialLockTransfer.TransferSize [in]

The size, in bytes, of the memory information to transfer.

### -field SpecialLockTransfer.Source [in]

A structure that describes the source allocation. This structure contains a **SegmentId** member and a union that contains either an offset into a segment of the source allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the source (**pMdl**).

### -field SpecialLockTransfer.Source.SegmentId [in]

The identifier of a segment within the source allocation, or zero if the source allocation is described by the **pMdl** member of the union that **Source** contains.

#### SpecialLockTransfer.Source.(unnamed union)

[in] A union that contains either an offset into a segment of the source allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the source (**pMdl**).

### -field SpecialLockTransfer.Source.SegmentAddress

[in] The source segment address, if the **SegmentId** member of **Source** is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: ```SegmentAddress = SegmentOffset + Segment.BaseAddr```.

### -field SpecialLockTransfer.Source.pMdl

[in] A pointer to a buffer that contains the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that describes the system memory pages for the source, if the **SegmentId** member of **Source** is zero.

### -field SpecialLockTransfer.Destination [in]

A structure that describes the destination allocation. This structure contains a **SegmentId** member and a union that contains either an offset into a segment of the destination allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the destination (**pMdl**).

### -field SpecialLockTransfer.Destination.SegmentId [in]

The identifier of a segment within the destination allocation, or zero if the destination allocation is described by the **pMdl** member of the union that **Destination** contains.

#### SpecialLockTransfer.Destination.(unnamed union)

[in] A union that contains either an offset into a segment of the destination allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the destination (**pMdl**).

### -field SpecialLockTransfer.Destination.SegmentAddress

[in] The destination segment address, if the **SegmentId** member of **Destination** is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: ```SegmentAddress = SegmentOffset + Segment.BaseAddr```.

### -field SpecialLockTransfer.Destination.pMdl

[in] A pointer to a buffer that contains the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that describes the system memory pages for the destination, if the **SegmentId** member of **Destination** is zero.

### -field SpecialLockTransfer.Flags [in]

A [**DXGK_TRANSFERFLAGS**](ns-d3dkmddi-_dxgk_transferflags.md) structure that identifies, in bit-field flags, the type of special-lock-transfer operation to perform.

### -field SpecialLockTransfer.SwizzlingRangeId [in]

A UINT value that identifies the swizzling range.

### -field SpecialLockTransfer.SwizzlingRangeData [in]

A UINT value that specifies swizzling range data.

### -field InitContextResource [in]

A structure that describes the context initialization operation. Supported beginning with Windows 8.

### -field InitContextResource.hAllocation [in]

A handle to the context allocation that was created when the driver called [**DxgkCbCreateContextAllocation**](nc-d3dkmddi-dxgkcb_createcontextallocation.md). The handle to this allocation is returned in the **hAllocation** member of the [**DXGKARGCB_CREATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_createcontextallocation.md) structure. The driver passes a pointer to this structure in the **ContextAllocation** parameter when it calls **DxgkCbCreateContextAllocation**.

### -field InitContextResource.Destination [in]

A structure that describes the destination context allocation. This structure contains a **SegmentId** member and a union that contains either an offset into a segment of the destination context allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the destination (**pMdl**).

### -field InitContextResource.Destination.SegmentId [in]

The identifier of a segment within the destination context allocation, or zero if the destination context allocation is described by the **pMdl** member of the union that **Destination** contains.

#### InitContextResource.Destination.(unnamed union)

[in] A union that contains either an offset into a segment of the destination context allocation (**SegmentAddress**) or a pointer to an [**MDL**](../wdm/ns-wdm-_mdl.md) for the destination (**pMdl**).

### -field InitContextResource.Destination.SegmentAddress

[in] The destination segment address, if the **SegmentId** member of **Destination** is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: ```SegmentAddress = SegmentOffset + Segment.BaseAddr```.

### -field InitContextResource.Destination.pMdl

[in] A pointer to a buffer that contains the [**MDL**](../wdm/ns-wdm-_mdl.md) structure that describes the system memory pages for the destination, if the **SegmentId** member of **Destination** is zero.

### -field InitContextResource.Destination.VirtualAddress [in]

The virtual address of the destination context allocation. This address is valid during the lifetime of the context allocation.

Follow procedures in the Virtual addresses for destination context allocations" section of the [**DxgkCbCreateContextAllocation**](nc-d3dkmddi-dxgkcb_createcontextallocation.md) topic to ensure that the virtual address is valid.

### -field InitContextResource.Destination.GpuVirtualAddress

GPU virtual address of the context resource to initialize.

### -field TransferVirtual

A [**DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL**](ns-d3dkmddi-_dxgk_buildpagingbuffer_transfervirtual.md) structure that describes the operation used to transfer allocation content between locations in memory.

### -field FillVirtual

A [**DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL**](ns-d3dkmddi-_dxgk_buildpagingbuffer_fillvirtual.md) structure that describes the operation used to fill an allocation with a pattern.

### -field UpdatePageTable

A [**DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE**](ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable.md) structure that describes the operation used to update a page table.

### -field FlushTlb

A [**DXGK_BUILDPAGINGBUFFER_FLUSHTLB**](ns-d3dkmddi-_dxgk_buildpagingbuffer_flushtlb.md) structure that describes the operation used to flush the translation look-aside buffers.

### -field CopyPageTableEntries

A [**DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES**](ns-d3dkmddi-_dxgk_buildpagingbuffer_copypagetableentries.md) structure that describes the operation used copy page table entries from one location to another.

### -field UpdateContextAllocation

A [**DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgk_buildpagingbuffer_updatecontextallocation.md) structure that describes the operation used to update the content of a context or device allocation.

### -field NotifyResidency

A [**DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY**](ns-d3dkmddi-_dxgk_buildpagingbuffer_notifyresidency.md) structure that describes a residency allocation change operation.

### -field SignalMonitoredFence [in]

A [**DXGK_BUILDPAGINGBUFFER_SIGNALMONITOREDFENCE**](ns-d3dkmddi-_dxgkarg_signalmonitoredfence.md) structure that describes a GPU instruction to signal the paging monitored fence object to the DMA buffer. Available starting with Windows 10, version 1703 (WDDM 2.2).

### - field MapApertureSegment2

A structure that describes the map-aperture-segment operation using an ADL. See [IOMMU DMA remapping](/windows-hardware/drivers/display/iommu-dma-remapping) for more information.

### -field MapApertureSegment2.hDevice [in]

A handle to the device that owns the allocation that **hAllocation** specifies that is mapped into the aperture segment that **SegmentId** specifies.

For a shared allocation, **hDevice** is set to the device that the video memory manager determined to be the owner of the allocation.

**hDevice** is **NULL** for the primary allocation.

### -field MapApertureSegment2.hAllocation [in]

The driver handle to the allocation that is mapped into the aperture segment that **SegmentId** specifies.

**hAllocation** is **NULL** when a DMA buffer is mapped into the aperture segment because DMA buffers are not explicitly created by the driver.

### -field MapApertureSegment2.SegmentId [in]

The identifier of an aperture segment to configure.

### -field MapApertureSegment2.OffsetInPages [in]

The offset, in pages, from the beginning of the segment to the first pages to map.

### -field MapApertureSegment2.NumberOfPages [in]

The size of the range being mapped within the allocation, in pages.

### -field MapApertureSegment2.Adl [in]

A [**DXGK_ADL**](ns-d3dkmddi-dxgk_adl.md) structure with the address descriptor list (ADL) that describes the logical address mappings (pages) for the allocation memory. This ADL can be either contiguous or a page array; the driver must be able to handle both cases.

### -field MapApertureSegment2.Flags [in]

A [**DXGK_MAPAPERTUREFLAGS**](ns-d3dkmddi-_dxgk_mapapertureflags.md) structure that identifies, in bit-field flags, the type of map-aperture-segment operation to perform.

### -field MapApertureSegment2.AdlOffset [in]

The offset within the [ADL](ns-d3dkmddi-dxgk_adl.md) to the start of the range of logical addresses being mapped for the current operation, specified in system memory pages. If the ADL is a contiguous ADL, then the ADL's **BasePageNumber** member is the start address of a contiguous range of memory. Otherwise use the ADL's **Pages** member for non-contiguous memory.

### -field MapApertureSegment2.CpuVisibleAddress

If a driver's allocation was created with the [**MapApertureCpuVisible**](/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfoflags_wddm2_0) flag set, **CpuVisibleAddress** is a non-null pointer to a system-mapped, kernel-mode virtual address for [**DXGK_OPERATION_MAP_APERTURE_SEGMENT2**](ne-d3dkmddi-_dxgk_buildpagingbuffer_operation.md) operations. This address is valid as long as the allocation is mapped into the aperture segment and will be freed immediately after the corresponding **DXGK_OPERATION_UNMAP_APERTURE_SEGMENT** call for the same allocation.

If **MapApertureCpuVisible** is not specified, **CpuVisibleAddress** is NULL for [**DXGK_OPERATION_MAP_APERTURE_SEGMENT2**](ne-d3dkmddi-_dxgk_buildpagingbuffer_operation.md) operations.

### -field Reserved

This member is reserved and should not be used.

### -field Reserved.Reserved

This member is reserved and should not be used.

### -field hSystemContext [in]

A handle to the system context for the paging operation.

### -field DmaBufferGpuVirtualAddress

A **D3DGPU_VIRTUAL_ADDRESS** data type that indicates the virtual address where the DMA buffer was paged in. If the physical address is zero, the DMA buffer is not correctly paged in.

### -field DmaBufferWriteOffset

The current operation offset in bytes from the start of the DMA buffer.

## -remarks

MDL is defined in the [Windows Driver Model (WDM)](/windows-hardware/drivers/kernel/using-mdls) documentation.

WDDM synchronization class:

* [First Level GPU Scheduler Class](/windows-hardware/drivers/display/threading-and-synchronization-first-level) for [BuildPagingBuffer](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) submission type.

## -see-also

[**DXGKARGCB_CREATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgkargcb_createcontextallocation.md)

[**DXGKARG_CREATEALLOCATION**](ns-d3dkmddi-_dxgkarg_createallocation.md)

[**DXGK_ALLOCATIONINFO**](ns-d3dkmddi-_dxgk_allocationinfo.md)

[**DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES**](ns-d3dkmddi-_dxgk_buildpagingbuffer_copypagetableentries.md)

[**DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL**](ns-d3dkmddi-_dxgk_buildpagingbuffer_fillvirtual.md)

[**DXGK_BUILDPAGINGBUFFER_FLUSHTLB**](ns-d3dkmddi-_dxgk_buildpagingbuffer_flushtlb.md)

[**DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY**](ns-d3dkmddi-_dxgk_buildpagingbuffer_notifyresidency.md)

[**DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL**](ns-d3dkmddi-_dxgk_buildpagingbuffer_transfervirtual.md)

[**DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION**](ns-d3dkmddi-_dxgk_buildpagingbuffer_updatecontextallocation.md)

[**DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE**](ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable.md)

[**DXGK_DISCARDCONTENTFLAGS**](ns-d3dkmddi-_dxgk_discardcontentflags.md)

[**DXGK_MAPAPERTUREFLAGS**](ns-d3dkmddi-_dxgk_mapapertureflags.md)

[**DXGK_TRANSFERFLAGS**](ns-d3dkmddi-_dxgk_transferflags.md)

[**DxgkCbCreateContextAllocation**](nc-d3dkmddi-dxgkcb_createcontextallocation.md)

[**DxgkDdiBuildPagingBuffer**](nc-d3dkmddi-dxgkddi_buildpagingbuffer.md)

[**DxgkDdiCreateAllocation**](nc-d3dkmddi-dxgkddi_createallocation.md)

[**MDL**](../wdm/ns-wdm-_mdl.md)

[**MmGetMdlPfnArray**](/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetmdlpfnarray

[**pfnLockCb**](../d3dumddi/nc-d3dumddi-pfnd3dddi_lockcb.md)
