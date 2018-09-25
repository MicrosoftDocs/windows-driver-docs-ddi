---
UID: NS:d3dkmddi._DXGKARGCB_CREATECONTEXTALLOCATION
title: "_DXGKARGCB_CREATECONTEXTALLOCATION"
author: windows-driver-content
description: Specifies the allocation attributes of a GPU context or device-specific context.
old-location: display\dxgkargcb_createcontextallocation.htm
ms.assetid: 2f5338a9-2a53-4fee-af6a-8a052ef8c423
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: "*INOUT_PDXGKARGCB_CREATECONTEXTALLOCATION, DXGKARGCB_CREATECONTEXTALLOCATION, DXGKARGCB_CREATECONTEXTALLOCATION structure [Display Devices], _DXGKARGCB_CREATECONTEXTALLOCATION, d3dkmddi/DXGKARGCB_CREATECONTEXTALLOCATION, display.dxgkargcb_createcontextallocation"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGKARGCB_CREATECONTEXTALLOCATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_CREATECONTEXTALLOCATION
---

# _DXGKARGCB_CREATECONTEXTALLOCATION structure


## -description


Specifies the allocation attributes of a GPU context or device-specific context.


## -struct-fields




### -field ContextAllocationFlags

[in] A <a href="https://msdn.microsoft.com/e80a314d-cef1-4289-84db-0a6b6531ae5f">DXGK_CREATECONTEXTALLOCATIONFLAGS</a> structure that specifies the properties of the allocation.


### -field hAdapter

[in] A handle to the graphics adapter for which the context allocation is created.


### -field hDevice

[in] A handle to the display device that was originally passed by the DirectX graphics subsystem to the display miniport driver's <a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a> function.

<div class="alert"><b>Note</b>  The member is set to <b>NULL</b> for a system device.</div>
<div> </div>

### -field hContext

[in] If <b>ContextAllocationFlags.SharedAcrossContexts</b> is set to a value of 0,
                                                                this member contains the value assigned by the DirectX graphics subsystem for the context that was passed to
                                                                the <a href="https://msdn.microsoft.com/b6b142a4-20eb-4368-bd7f-8a25f4fe48ca">DxgkCbCreateContextAllocation</a> function.

If <b>ContextAllocationFlags.SharedAcrossContexts</b> is set to a value of 1, this member should be set to <b>NULL</b>.

<div class="alert"><b>Note</b>  The member is also set to <b>NULL</b> for a system context.</div>
<div> </div>

### -field hDriverAllocation

A handle created by the display miniport driver that identifies the created allocation. The value of this member is subsequently passed as the <b>Transfer.hAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a> structure that is pointed to by the <i>pBuildPagingBuffer</i> parameter of the <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a> function.


### -field Size

[in] The size, in bytes, that is required for the allocation.


### -field Alignment

[in] The required alignment, in bytes, for the allocation.



### -field SupportedSegmentSet

[in] Segment identifiers that the display miniport driver can set in the <b>PreferredSegment</b> member for read or write operations.


### -field EvictionSegmentSet

[in] Identifiers of segments that can be used for eviction.


### -field PreferredSegment

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562047">DXGK_SEGMENTPREFERENCE</a> structure that indicates the preferred segment identifiers that the display miniport driver requests that the video memory manager use to page-in the allocation.


### -field HintedBank

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562032">DXGK_SEGMENTBANKPREFERENCE</a> structure that indicates the bank ordering preferences that the display miniport driver requests that the video memory manager use to page-in the allocation.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560966">DXGK_ALLOCATIONINFOFLAGS</a> structure that identifies properties for an allocation in bit-field flags. These properties indicate the type of allocation to create. The display miniport driver specifies these flags for the video memory manager. See Remarks for restrictions on flag values.


### -field hAllocation

[out] A handle that has been assigned by the DirectX graphics subsystem to the allocation. This value is subsequently passed as the <b>hAllocation</b> parameter of the  <a href="https://msdn.microsoft.com/f613e019-0b6d-43fc-a802-a6cd3803a00d">DxgkCbDestroyContextAllocation</a> function.


### -field PhysicalAdapterIndex

 




## -remarks



The display miniport driver calls <a href="https://msdn.microsoft.com/b6b142a4-20eb-4368-bd7f-8a25f4fe48ca">DxgkCbCreateContextAllocation</a> to allocate a GPU context or device-specific context. When the driver calls this function, it passes a pointer to a <b>DXGKARGCB_CREATECONTEXTALLOCATION</b> structure through the <i>ContextAllocation</i> parameter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560966">DXGK_ALLOCATIONINFOFLAGS</a>



<a href="https://msdn.microsoft.com/e80a314d-cef1-4289-84db-0a6b6531ae5f">DXGK_CREATECONTEXTALLOCATIONFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562032">DXGK_SEGMENTBANKPREFERENCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562047">DXGK_SEGMENTPREFERENCE</a>



<a href="https://msdn.microsoft.com/b6b142a4-20eb-4368-bd7f-8a25f4fe48ca">DxgkCbCreateContextAllocation</a>
 

 

