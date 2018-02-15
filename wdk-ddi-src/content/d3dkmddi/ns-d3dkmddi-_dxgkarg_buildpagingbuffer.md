---
UID: NS:d3dkmddi._DXGKARG_BUILDPAGINGBUFFER
title: "_DXGKARG_BUILDPAGINGBUFFER"
author: windows-driver-content
description: The DXGKARG_BUILDPAGINGBUFFER structure describes parameters for building a paging buffer that is used in a memory-transfer operation.
old-location: display\dxgkarg_buildpagingbuffer.htm
old-project: display
ms.assetid: dc0de06b-d495-4ce2-b0e2-a6fefd6c8e0c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGKARG_BUILDPAGINGBUFFER, DXGKARG_BUILDPAGINGBUFFER, DmStructs_06cb7ec2-482d-41ba-b550-3c4f27d36070.xml, display.dxgkarg_buildpagingbuffer, DXGKARG_BUILDPAGINGBUFFER_OPERATION, _DXGKARG_BUILDPAGINGBUFFER, *IN_PDXGKARG_BUILDPAGINGBUFFER, DXGK_BUILDPAGINGBUFFER_OPERATION, DXGKARG_BUILDPAGINGBUFFER structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_BUILDPAGINGBUFFER
product: Windows
targetos: Windows
req.typenames: DXGKARG_BUILDPAGINGBUFFER
---

# _DXGKARG_BUILDPAGINGBUFFER structure


## -description


The <b>DXGKARG_BUILDPAGINGBUFFER</b> structure describes parameters for building a paging buffer that is used in a memory-transfer operation.


## -syntax


````
typedef struct _DXGKARG_BUILDPAGINGBUFFER {
  VOID                             *pDmaBuffer;
  UINT                             DmaSize;
  VOID                             *pDmaBufferPrivateData;
  UINT                             DmaBufferPrivateDataSize;
  DXGK_BUILDPAGINGBUFFER_OPERATION Operation;
  UINT                             MultipassOffset;
  union {
    struct {
      HANDLE             hAllocation;
      UINT               TransferOffset;
      SIZE_T             TransferSize;
      struct {
        UINT SegmentId;
        union {
          LARGE_INTEGER SegmentAddress;
          MDL           *pMdl;
        };
      } Source;
      struct {
        UINT SegmentId;
        union {
          LARGE_INTEGER SegmentAddress;
          MDL           *pMdl;
        };
      } Destination;
      DXGK_TRANSFERFLAGS Flags;
      UINT               MdlOffset;
    } Transfer;
    struct {
      HANDLE hAllocation;
      SIZE_T FillSize;
      UINT   FillPattern;
      struct {
        UINT          SegmentId;
        LARGE_INTEGER SegmentAddress;
      } Destination;
    } Fill;
    struct {
      HANDLE                   hAllocation;
      DXGK_DISCARDCONTENTFLAGS Flags;
      UINT                     SegmentId;
      PHYSICAL_ADDRESS         SegmentAddress;
    } DiscardContent;
    struct {
      UINT             SegmentId;
      PHYSICAL_ADDRESS PhysicalAddress;
    } ReadPhysical;
    struct {
      UINT             SegmentId;
      PHYSICAL_ADDRESS PhysicalAddress;
    } WritePhysical;
    struct {
      HANDLE                hDevice;
      HANDLE                hAllocation;
      UINT                  SegmentId;
      SIZE_T                OffsetInPages;
      SIZE_T                NumberOfPages;
      PMDL                  pMdl;
      DXGK_MAPAPERTUREFLAGS Flags;
      ULONG                 MdlOffset;
    } MapApertureSegment;
    struct {
      HANDLE           hDevice;
      HANDLE           hAllocation;
      UINT             SegmentId;
      SIZE_T           OffsetInPages;
      SIZE_T           NumberOfPages;
      PHYSICAL_ADDRESS DummyPage;
    } UnmapApertureSegment;
    struct {
      HANDLE             hAllocation;
      UINT               TransferOffset;
      SIZE_T             TransferSize;
      struct {
        UINT SegmentId;
        union {
          LARGE_INTEGER SegmentAddress;
          MDL           *pMdl;
        };
      } Source;
      struct {
        UINT SegmentId;
        union {
          LARGE_INTEGER SegmentAddress;
          MDL           *pMdl;
        };
      } Destination;
      DXGK_TRANSFERFLAGS Flags;
      UINT               SwizzlingRangeId;
      UINT               SwizzlingRangeData;
    } SpecialLockTransfer;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
    struct {
      HANDLE hAllocation;
      struct {
        UINT                    SegmentId;
        union {
          LARGE_INTEGER SegmentAddress;
          MDL           *pMdl;
        };
        PVOID                   VirtualAddress;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
        D3DGPU_VIRTUAL_ADDRESS  GpuVirtualAddress;
#endif 
      } Destination;
    } InitContextResource;
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
    DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL         TransferVirtual;
    DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL             FillVirtual;
    DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE         UpdatePageTable;
    DXGK_BUILDPAGINGBUFFER_FLUSHTLB                FlushTlb;
    DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES    CopyPageTableEntries;
    DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION UpdateContextAllocation;
    DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY         NotifyResidency;
#endif 
    struct {
      UINT Reserved[64];
    } Reserved;
  };
  HANDLE                           hSystemContext;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  D3DGPU_VIRTUAL_ADDRESS           DmaBufferGpuVirtualAddress;
#endif 
} DXGKARG_BUILDPAGINGBUFFER;
````


## -struct-fields




### -field pDmaBuffer

[in/out] A virtual address to the first available byte in the paging buffer. When the driver is first called with a new paging buffer, this virtual address is aligned on 4 KB. The driver tightly packs operations in the paging buffer until the paging buffer is full and then uses a new paging buffer. Therefore, if the graphics processing unit (GPU) requires a specific alignment for a paging-buffer submission, the driver should enforce this alignment by padding the operations that it writes to the paging buffer. Before the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function returns, the driver should update <b>pDmaBuffer</b> to point past the last byte that is written to the paging buffer. 


### -field DmaSize

[in/out] The size, in bytes, of the paging buffer that <b>pDmaBuffer</b> specifies.


### -field pDmaBufferPrivateData

[in/out] A pointer to a driver-resident private data structure that is associated with the direct memory access (DMA) buffer (that is, paging buffer) that <b>pDmaBuffer</b> specifies.


### -field DmaBufferPrivateDataSize

[in/out] The number of bytes that remain in the private data structure that <b>pDmaBufferPrivateData</b> points to for the current operation.


### -field Operation

[in] A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_buildpagingbuffer_operation.md">DXGK_BUILDPAGINGBUFFER_OPERATION</a>-typed value that indicates the type of memory operation to perform. 


### -field MultipassOffset

[in/out] A UINT value that specifies the progress of the paging operation if multiple paging buffers are required. The driver sets this value to indicate a split into multiple paging buffers for more than one transfer operation. For example, the driver can store the page number that was last transferred for a paged-based transfer. 


### -field Transfer

[in] A structure that describes the transfer operation.


### -field Transfer.hAllocation

[in] A handle to the allocation that the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function previously returned in the <b>hAllocation</b> member of a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure, which is part of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure's <b>pAllocationInfo</b> member. The allocation handle points to a buffer that contains private driver data for the transfer.


### -field Transfer.TransferOffset

[in] The offset, in bytes, of the first page within the allocation that is transferred. This offset is applied only to a location that a segment location describes. This offset does not apply to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> description of a memory range. If the driver requires more than one paging buffer to complete the transfer (that is, the driver returns STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER from its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function), <b>TransferOffset</b> is the same for each call to <i>DxgkDdiBuildPagingBuffer</i> for this transfer.


### -field Transfer.TransferSize

[in] The size, in bytes, of the memory information to transfer.


### -field Transfer.Source

[in] A structure that describes the source allocation. This structure contains a <b>SegmentId</b> member and a union that contains either an offset into a segment of the source allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the source (<b>pMdl</b>).


### -field Transfer.Source.SegmentId

[in] The identifier of a segment within the source allocation, or zero if the source allocation is described by the <b>pMdl</b> member of the union that <b>Source</b> contains.


### -field Transfer.Source.SegmentAddress

[in] The source segment address, if the <b>SegmentId</b> member of <b>Source</b> is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: <code>SegmentAddress = SegmentOffset + Segment.BaseAddr</code>.


### -field Transfer.Source.pMdl

[in] A pointer to a buffer that contains the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the system memory pages for the source, if the <b>SegmentId</b> member of <b>Source</b> is zero.


### -field Transfer.Destination

[in] A structure that describes the destination allocation. This structure contains a <b>SegmentId</b> member and a union that contains either an offset into a segment of the destination allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the destination (<b>pMdl</b>).


### -field Transfer.Destination.SegmentId

[in] The identifier of a segment within the destination allocation, or zero if the destination allocation is described by the <b>pMdl</b> member of the union that <b>Destination</b> contains.


### -field Transfer.Destination.SegmentAddress

[in] The destination segment address, if the <b>SegmentId</b> member of <b>Destination</b> is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: <code>SegmentAddress = SegmentOffset + Segment.BaseAddr</code>.


### -field Transfer.Destination.pMdl

[in] A pointer to a buffer that contains the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the system memory pages for the destination, if the <b>SegmentId</b> member of <b>Destination</b> is zero.


### -field Transfer.Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_transferflags.md">DXGK_TRANSFERFLAGS</a> structure that identifies, in bit-field flags, the type of special-lock-transfer operation to perform.


### -field Transfer.MdlOffset

[in] The offset, in system memory pages, within the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that the <b>pMdl</b> member points to, to the first system memory page for the current operation. The driver can obtain the physical address of the first system memory page by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554537">MmGetMdlPfnArray</a> function as follows. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MmGetMdlPfnArray(pMdl)[MdlOffset];</pre>
</td>
</tr>
</table></span></div>

### -field Fill

[in] A structure that describes the fill operation.


### -field Fill.hAllocation

[in] A handle to the allocation that contains content to fill.


### -field Fill.FillSize

[in] The size, in bytes, of the memory information to fill.


### -field Fill.FillPattern

[in] The pattern to fill the destination with. The video memory manager uses this information to initialize video memory to a specific pattern when an allocation without content is first paged in. In this case, no source exists for the fill request—only a destination exists.


### -field Fill.Destination

[in] A structure that describes the destination allocation for the fill operation.


### -field Fill.Destination.SegmentId

[in] The identifier of a segment within the destination allocation.


### -field Fill.Destination.SegmentAddress

[in] The destination segment address. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: <code>SegmentAddress = SegmentOffset + Segment.BaseAddr</code>.


### -field DiscardContent

[in] A structure that describes the discard-content operation.


### -field DiscardContent.hAllocation

[in] A handle to the allocation that contains content to discard.


### -field DiscardContent.Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_discardcontentflags.md">DXGK_DISCARDCONTENTFLAGS</a> structure that identifies, in bit-field flags, the type of discard-content operation to perform.


### -field DiscardContent.SegmentId

[in] The identifier of a segment within the allocation to discard content from.


### -field DiscardContent.SegmentAddress

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the segment address. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: <code>SegmentAddress = SegmentOffset + Segment.BaseAddr</code>. This location is where content is discarded from.


### -field ReadPhysical

[in] A structure that describes the read-physical operation.


### -field ReadPhysical.SegmentId

[in] The identifier of a segment that data is read from.


### -field ReadPhysical.PhysicalAddress

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address, within the segment that <b>SegmentId</b> specifies, where the data is read.


### -field WritePhysical

[in] A structure that describes the write-physical operation.


### -field WritePhysical.SegmentId

[in] The identifier of a segment to which data is written.


### -field WritePhysical.PhysicalAddress

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address, within the segment that <b>SegmentId</b> specifies, where the data is written.


### -field MapApertureSegment

[in] A structure that describes the map-aperture-segment operation.


### -field MapApertureSegment.hDevice

[in] A handle to the device that owns the allocation that <b>hAllocation</b> specifies that is mapped into the aperture segment that <b>SegmentId</b> specifies. 

For a shared allocation, <b>hDevice</b> is set to the device that the video memory manager determined to be the owner of the allocation.

<b>hDevice</b> is <b>NULL</b> for the primary allocation. 


### -field MapApertureSegment.hAllocation

[in] A handle to the allocation that is mapped into the aperture segment that <b>SegmentId</b> specifies. 

<b>hAllocation</b> is <b>NULL</b> when a DMA buffer is mapped into the aperture segment because DMA buffers are not explicitly created by the driver.


### -field MapApertureSegment.SegmentId

[in] The identifier of an aperture segment to configure.


### -field MapApertureSegment.OffsetInPages

[in] The offset, in pages, from the beginning of the segment to the first pages to map.


### -field MapApertureSegment.NumberOfPages

[in] The number of pages to map.


### -field MapApertureSegment.pMdl

[in] A pointer to a buffer that contains the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the physical system memory pages to map into the aperture segment.


### -field MapApertureSegment.Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_mapapertureflags.md">DXGK_MAPAPERTUREFLAGS</a> structure that identifies, in bit-field flags, the type of map-aperture-segment operation to perform.


### -field MapApertureSegment.MdlOffset

[in] The offset, in system memory pages, within the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that the <b>pMdl</b> member points to, to the first system memory page for the current operation. The driver can obtain the physical address of the first system memory page by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554537">MmGetMdlPfnArray</a> function as follows. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MmGetMdlPfnArray(pMdl)[MdlOffset];</pre>
</td>
</tr>
</table></span></div>

### -field UnmapApertureSegment

[in] A structure that describes the unmap-aperture-segment operation.


### -field UnmapApertureSegment.hDevice

[in] A handle to the device that owns the allocation that <b>hAllocation</b> specifies that is unmapped from the aperture segment that <b>SegmentId</b> specifies. 

For a shared allocation, <b>hDevice</b> is set to the device that the video memory manager determined to be the owner of the allocation. 

<b>hDevice</b> is <b>NULL</b> for the primary allocation. 


### -field UnmapApertureSegment.hAllocation

[in] A handle to the allocation that is unmapped from the aperture segment that <b>SegmentId</b> specifies. 

<b>hAllocation</b> is <b>NULL</b> when a DMA buffer is unmapped from the aperture segment because DMA buffers are not explicitly created by the driver.


### -field UnmapApertureSegment.SegmentId

[in] The identifier of an aperture segment to configure.


### -field UnmapApertureSegment.OffsetInPages

[in] The offset, in pages, from the beginning of the segment to the first pages to unmap.


### -field UnmapApertureSegment.NumberOfPages

[in] The number of pages to unmap.


### -field UnmapApertureSegment.DummyPage

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address of the placeholder page where the driver should map the range that is unmapped.


### -field SpecialLockTransfer

[in] A structure that describes the special-lock-transfer operation.


### -field SpecialLockTransfer.hAllocation

[in] A handle to the allocation that the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function previously returned in the <b>hAllocation</b> member of a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure, which is part of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure's <b>pAllocationInfo</b> member. The allocation handle points to a buffer that contains private driver data for the special-lock transfer.


### -field SpecialLockTransfer.TransferOffset

[in] The offset, in bytes, of the first page within the allocation that is transferred. This offset is applied only to a location that a segment location describes. This offset does not apply to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a> description of a memory range. If the driver requires more than one paging buffer to complete the transfer (that is, the driver returns STATUS_GRAPHICS_INSUFFICIENT_DMA_BUFFER from its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function), <b>TransferOffset</b> is the same for each call to <i>DxgkDdiBuildPagingBuffer</i> for this transfer.


### -field SpecialLockTransfer.TransferSize

[in] The size, in bytes, of the memory information to transfer.


### -field SpecialLockTransfer.Source

[in] A structure that describes the source allocation. This structure contains a <b>SegmentId</b> member and a union that contains either an offset into a segment of the source allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the source (<b>pMdl</b>).



##### Source.(unnamed union)

[in] A union that contains either an offset into a segment of the source allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the source (<b>pMdl</b>).



###### (unnamed union).SegmentAddress

[in] The source segment address, if the <b>SegmentId</b> member of <b>Source</b> is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: <code>SegmentAddress = SegmentOffset + Segment.BaseAddr</code>.



###### (unnamed union).pMdl

[in] A pointer to a buffer that contains the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the system memory pages for the source, if the <b>SegmentId</b> member of <b>Source</b> is zero.


### -field SpecialLockTransfer.Source.SegmentId

[in] The identifier of a segment within the source allocation, or zero if the source allocation is described by the <b>pMdl</b> member of the union that <b>Source</b> contains.


### -field SpecialLockTransfer.Source.SegmentAddress

 


### -field SpecialLockTransfer.Source.pMdl

 


### -field SpecialLockTransfer.Destination

[in] A structure that describes the destination allocation. This structure contains a <b>SegmentId</b> member and a union that contains either an offset into a segment of the destination allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the destination (<b>pMdl</b>).



##### Destination.(unnamed union)

[in] A union that contains either an offset into a segment of the destination allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the destination (<b>pMdl</b>).



###### (unnamed union).SegmentAddress

[in] The destination segment address, if the <b>SegmentId</b> member of <b>Destination</b> is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: <code>SegmentAddress = SegmentOffset + Segment.BaseAddr</code>.



###### (unnamed union).pMdl

[in] A pointer to a buffer that contains the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the system memory pages for the destination, if the <b>SegmentId</b> member of <b>Destination</b> is zero.


### -field SpecialLockTransfer.Destination.SegmentId

[in] The identifier of a segment within the destination allocation, or zero if the destination allocation is described by the <b>pMdl</b> member of the union that <b>Destination</b> contains.


### -field SpecialLockTransfer.Destination.SegmentAddress

 


### -field SpecialLockTransfer.Destination.pMdl

 


### -field SpecialLockTransfer.Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_transferflags.md">DXGK_TRANSFERFLAGS</a> structure that identifies, in bit-field flags, the type of special-lock-transfer operation to perform.


### -field SpecialLockTransfer.SwizzlingRangeId

[in] A UINT value that identifies the swizzling range.


### -field SpecialLockTransfer.SwizzlingRangeData

[in] A UINT value that specifies swizzling range data.


### -field InitContextResource

[in] A structure that describes the context initialization operation.


Supported beginning with Windows 8.


### -field InitContextResource.hAllocation

[in] A handle to the context allocation that was created when the driver called <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>. The handle to this allocation is returned in the <b>hAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure. The driver passes a pointer to this structure in the 

<i>ContextAllocation</i> parameter when it calls <b>DxgkCbCreateContextAllocation</b>.


### -field InitContextResource.Destination

[in] A structure that describes the destination context allocation. This structure contains a <b>SegmentId</b> member and a union that contains either an offset into a segment of the destination context allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the destination (<b>pMdl</b>).



##### Destination.(unnamed union)

[in] A union that contains either an offset into a segment of the destination context allocation (<b>SegmentAddress</b>) or a pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> for the destination (<b>pMdl</b>).



###### (unnamed union).SegmentAddress

[in] The destination segment address, if the <b>SegmentId</b> member of <b>Destination</b> is nonzero. The DirectX graphics kernel subsystem computes the segment address as the sum of the segment offset and the base address of the segment: <code>SegmentAddress = SegmentOffset + Segment.BaseAddr</code>.



###### (unnamed union).pMdl

[in] A pointer to a buffer that contains the <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> structure that describes the system memory pages for the destination, if the <b>SegmentId</b> member of <b>Destination</b> is zero.


### -field InitContextResource.Destination.SegmentId

[in] The identifier of a segment within the destination context allocation, or zero if the destination context allocation is described by the <b>pMdl</b> member of the union that <b>Destination</b> contains.


### -field InitContextResource.Destination.SegmentAddress

 


### -field InitContextResource.Destination.pMdl

 


### -field InitContextResource.Destination.VirtualAddress

[in] The virtual address of the destination context allocation. This address is valid during the lifetime of the context allocation.

Follow procedures in  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">Virtual addresses for destination context allocations</a> in the <i>DxgkCbCreateContextAllocation</i> topic to ensure that the virtual address is valid.


### -field InitContextResource.Destination.GpuVirtualAddress

 


### -field TransferVirtual

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_transfervirtual.md">DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL</a> structure that describes the operation used to transfer allocation content between locations in memory. 


### -field FillVirtual

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_fillvirtual.md">DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL</a> structure that describes the operation used to fill an allocation with a pattern. 


### -field UpdatePageTable

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable.md">DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</a> structure that describes the operation used to update a page table. 


### -field FlushTlb

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_flushtlb.md">DXGK_BUILDPAGINGBUFFER_FLUSHTLB</a> structure that describes the operation used to flush the translation look-aside buffers. 


### -field CopyPageTableEntries

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_copypagetableentries.md">DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES</a> structure that describes the operation used copy page table entries from one location to another. 


### -field UpdateContextAllocation

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_updatecontextallocation.md">DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION</a> structure that describes the operation used to update the content of a context or device allocation.


### -field NotifyResidency

A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_notifyresidency.md">DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY</a> structure that describes a residency allocation change operation. 


### -field SignalMonitoredFence

 


### -field Reserved

This member is reserved and should not be used.


### -field Reserved.Reserved

This member is reserved and should not be used.


### -field hSystemContext

[in] A handle to the system context for the paging operation.


### -field DmaBufferGpuVirtualAddress


### -field DmaBufferWriteOffset

 




## -remarks



MDL is defined in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565698">Windows Driver Model (WDM)</a> documentation.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_updatecontextallocation.md">DXGK_BUILDPAGINGBUFFER_UPDATECONTEXTALLOCATION</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_copypagetableentries.md">DXGK_BUILDPAGINGBUFFER_COPYPAGETABLEENTRIES</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_notifyresidency.md">DXGK_BUILDPAGINGBUFFER_NOTIFYRESIDENCY</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_discardcontentflags.md">DXGK_DISCARDCONTENTFLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_flushtlb.md">DXGK_BUILDPAGINGBUFFER_FLUSHTLB</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_transfervirtual.md">DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_fillvirtual.md">DXGK_BUILDPAGINGBUFFER_FILLVIRTUAL</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554537">MmGetMdlPfnArray</a>



<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_mapapertureflags.md">DXGK_MAPAPERTUREFLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_transferflags.md">DXGK_TRANSFERFLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_buildpagingbuffer_updatepagetable.md">DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_BUILDPAGINGBUFFER structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

