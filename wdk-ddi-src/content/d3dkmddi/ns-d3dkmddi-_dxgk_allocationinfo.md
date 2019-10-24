---
UID: NS:d3dkmddi._DXGK_ALLOCATIONINFO
title: _DXGK_ALLOCATIONINFO (d3dkmddi.h)
description: The DXGK_ALLOCATIONINFO structure describes parameters for creating an allocation.
old-location: display\dxgk_allocationinfo.htm
ms.assetid: d5767bd3-11f8-45a7-b760-3ed51c54c044
ms.date: 05/10/2018
ms.keywords: DXGK_ALLOCATIONINFO, DXGK_ALLOCATIONINFO structure [Display Devices], DmStructs_f571b666-75fd-477a-a8a7-673033d9284e.xml, _DXGK_ALLOCATIONINFO, d3dkmddi/DXGK_ALLOCATIONINFO, display.dxgk_allocationinfo
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_ALLOCATIONINFO"
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
- DXGK_ALLOCATIONINFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_ALLOCATIONINFO
---

# _DXGK_ALLOCATIONINFO structure


## -description


The DXGK_ALLOCATIONINFO structure describes parameters for creating an allocation.


## -struct-fields




### -field pPrivateDriverData

[in] A pointer to a block of private data. This data is for each allocation and is distinct from the <b>pPrivateDriverData</b> member in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a> structure. The user-mode display driver might pass this data to the display miniport driver. However, if  the Microsoft DirectX graphics kernel subsystem passes this data to describe the shared primary or other lockable surface, the data is passed as the first element of the array in the <b>pAllocationInfo</b> member of DXGKARG_CREATEALLOCATION.


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data in <b>pPrivateDriverData</b>.


### -field Alignment

[out] The required alignment, in bytes, for the allocation.


### -field Size

[out] The size, in bytes, that is required for the allocation. The size value is expanded to a multiple of the native host page size (for example, 4 KB on the x86 architecture). The display miniport driver specifies the allocation size to the video memory manager.


### -field PitchAlignedSize

[out] The size, in bytes, of the allocation when it is located in a pitch-aligned segment, which is specified by the <b>PitchAlignment</b> bit-field flag in the <b>Flags</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentdescriptor">DXGK_SEGMENTDESCRIPTOR</a> structure for the segment. If the allocation is not supported in a pitch-aligned segment (graphics processing units [GPUs] commonly do not support this type of segment), the driver should set the value in <b>PitchAlignedSize</b> to zero. If the driver specifies a nonzero value in <b>PitchAlignedSize</b>, the value must be greater than or equal to the value in the <b>Size</b> member.


### -field HintedBank

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentbankpreference">DXGK_SEGMENTBANKPREFERENCE</a> structure that indicates the bank ordering preferences that the display miniport driver requests that the video memory manager use to page-in the allocation. If this member is specified, the video memory manager uses banking information about the most preferred segment, which is specified by the <b>SegmentId0</b> member of the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff562047(v=vs.85)">DXGK_SEGMENTPREFERENCE</a> structure that the <b>PreferredSegment</b> member specifies.


### -field PreferredSegment

[out] A <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff562047(v=vs.85)">DXGK_SEGMENTPREFERENCE</a> structure that indicates preferred segments identifiers that the display miniport driver requests that the video memory manager use to page-in the allocation.


### -field SupportedReadSegmentSet

[out] Segment identifiers that the display miniport driver can set in the <b>PreferredSegment</b> member for read operations. The segments that these identifiers indicate are segments that the display miniport driver requests that the video memory manager use to page-in the allocation for read operations, regardless of performance. Setting bit 0 indicates that the first segment is supported, setting bit 1 indicates that the second segment is supported, and so on. 

The display miniport driver can set preferences only for segments that are supported for read operations. The video memory manager asserts if the driver attempts to set preferences for unsupported segments in the <b>PreferredSegment</b> member.


### -field SupportedWriteSegmentSet

[out] Segment identifiers that the display miniport driver can set in the <b>PreferredSegment</b> member for write operations. The segments that these identifiers indicate are segments that the display miniport driver requests that the video memory manager use to page-in the allocation for write operations, regardless of performance. Setting bit 0 indicates that the first segment is supported, setting bit 1 indicates that the second segment is supported, and so on. 

The display miniport driver can set preferences only for segments that are supported for write operations. The video memory manager asserts if the driver attempts to set preferences for unsupported segments in the <b>PreferredSegment</b> member.


### -field EvictionSegmentSet

[out] Identifiers of segments that can be used for eviction. Setting bit 0 indicates that the first segment can be used for eviction, setting bit 1 indicates that the second segment can be used for eviction, and so on. 

Only aperture segments can be specified by this member. If the driver specifies valid segments to be used for eviction, the video memory manager attempts to allocate resources in those aperture segments to accelerate the eviction process. If the driver specifies 0, the video memory manager calls the driver to transfer the content of an allocation directly to paged-locked system memory without mapping the underlying pages through an aperture segment.


### -field MaximumRenamingListLength

[out] The maximum length of the renaming list for the allocation. For more information about the renaming list, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/requesting-to-rename-an-allocation">Requesting to Rename an Allocation</a>.

Support for this member started with Windows 10 and the WDDM v2.


### -field PhysicalAdapterIndex

[out] The index of the physical adapter. 

Support for this member started with Windows 10 and the WDDM v2.


### -field hAllocation

[out] A handle to the allocation. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the allocation.


### -field Flags

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a> structure that identifies properties for an allocation in bit-field flags. These properties indicate the type of allocation to create. The display miniport driver specifies these flags for the video memory manager.


### -field FlagsWddm2

[out] The index of the physical adapter. 

Support for this member started with Windows 10 and WDDM 2.0.


### -field pAllocationUsageHint

[out] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationusagehint">DXGK_ALLOCATIONUSAGEHINT</a> structure that the memory manager uses to determine how to use the allocation.


### -field AllocationPriority

[out] A UINT value that specifies the starting priority level of the allocation. 

The driver determines the appropriate priority level for each allocation. For more information about priority levels, see the Remarks section of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setprioritycb">pfnSetPriorityCb</a> function. If priority level for allocations is not an issue to the driver, the driver should set all priority levels to <b>D3DDDI_ALLOCATIONPRIORITY_NORMAL</b>. Note that 0 is an invalid initial allocation priority. 


## -remarks



With the WDDM v2, the <b>DXGK_ALLOCATIONINFO</b> structure has been changed so that the read and write segment set are no longer differentiated. During surface creation the video memory manager will ignore the <b>SupportedReadSegmentSet</b> value and use only the segment set provide by <b>SupportedWriteSegmentSet</b>. Drivers should ensure that this value accurately represents the segment set that can be used by the allocation for its intended purpose.


Ignoring the supported read segment set does not mean that it is no longer supported, but simply that there should no longer be a difference between these sets, and the video memory manager will be allowed to choose an appropriate segment for any allocation from a single segment set.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_sharedprimarysurfacedata">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createallocation">DXGKARG_CREATEALLOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationlist">DXGK_ALLOCATIONLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationusagehint">DXGK_ALLOCATIONUSAGEHINT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentbankpreference">DXGK_SEGMENTBANKPREFERENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_segmentdescriptor">DXGK_SEGMENTDESCRIPTOR</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff562047(v=vs.85)">DXGK_SEGMENTPREFERENCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_render">DxgkDdiRender</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a>
 

 

