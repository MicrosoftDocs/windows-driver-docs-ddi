---
UID: NS:d3dkmddi._DXGK_CONTEXTINFO
title: "_DXGK_CONTEXTINFO"
author: windows-driver-content
description: The DXGK_CONTEXTINFO structure describes a device context.
old-location: display\dxgk_contextinfo.htm
tech.root: display
ms.assetid: 52c98ca7-8024-42d6-9001-1a7a69d24a95
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_CONTEXTINFO, DXGK_CONTEXTINFO structure [Display Devices], DmStructs_e95e533c-2156-4384-9e7e-718e7d61c458.xml, _DXGK_CONTEXTINFO, d3dkmddi/DXGK_CONTEXTINFO, display.dxgk_contextinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_CONTEXTINFO
product:
- Windows
targetos: Windows
req.typenames: DXGK_CONTEXTINFO
---

# _DXGK_CONTEXTINFO structure


## -description


The DXGK_CONTEXTINFO structure describes a device context.


## -struct-fields




### -field DmaBufferSize

The size, in bytes, of the buffer of hardware commands that is sent through direct memory access (DMA) to the graphics processing unit (GPU).

The DMA buffer can grow and shrink after the context is created; however, the DMA buffer can never shrink smaller than the starting size that <b>DmaBufferSize</b> specifies.  


### -field DmaBufferSegmentSet

 The identifiers of the segments where the DMA buffer should be made accessible to the GPU. 


### -field DmaBufferPrivateDataSize

The size, in bytes, of the driver-resident private data structure that is associated with each DMA buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero in <b>DmaBufferPrivateDataSize</b>, no memory is allocated for the private data structure.

The private data structure that is associated with a DMA buffer is initialized to zero when the DMA buffer is created. During the lifetime of the DMA buffer, the video memory manager never accesses the private data structure that is associated with the DMA buffer. 


### -field AllocationListSize

The starting number of elements in an array of allocations (that is, an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560975">DXGK_ALLOCATIONLIST</a> structures). This number is the starting number of allocations that the driver requests to be in the <b>pAllocationList</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557618">DXGKARG_PRESENT</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a> structures in calls to the driver's <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> and <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> functions, respectively.

The allocation list can grow and shrink after the context is created; however, the allocation list can never shrink smaller than the starting size that <b>AllocationListSize</b> specifies.  

<div class="alert"><b>Note</b>  If <a href="https://msdn.microsoft.com/library/windows/hardware/ff561037">DXGK_CREATECONTEXTFLAGS</a>.<b>GdiContext</b>  is set to 1, meaning that the context is created as a GDI-specific context,  <b>AllocationListSize</b> must be set to a value of 256.</div>
<div> </div>

### -field PatchLocationListSize

 The starting number of elements in an array of patch locations (that is, an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a> structures) for the device in user mode and kernel mode. This number is the starting number of patch locations that the driver requests to be in the <b>pPatchLocationListIn</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a> structures in calls to its <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> function.

The patch-location list can grow and shrink after the context is created; however, the patch-location list can never shrink smaller than the starting size that <b>PatchLocationListSize</b> specifies. 


### -field Reserved

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


### -field Caps

Describes optional features supported by the context.

Supported starting with Windows 10.


### -field PagingCompanionNodeId

Specifies the zero-based engine identifier of the engine to use for this context paging companion.

Supported starting with Windows 10.


## -remarks



A display miniport driver specifies values for the <b>DmaBufferSize</b> and <b>AllocationListSize</b> members to guarantee that:

<ul>
<li>
The Microsoft DirectX graphics subsystem can use only one direct memory access (DMA) buffer to display (by using the display miniport driver's <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> function) at least one <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure for all scenarios.

</li>
<li>
The sizes of DMA and allocation-list buffers are large enough to hold at least one command that cannot be split across multiple buffers.

</li>
<li>
The sizes of DMA and allocation-list buffers are large enough to avoid setup and DMA overhead. 

</li>
</ul>
The display miniport driver can specify only aperture segments in the <b>DmaBufferSegmentSet</b> member; if the driver specifies a memory segment, a context-creation failure occurs. 

If the driver sets <b>DmaBufferSegmentSet</b> to 0, the video memory manager allocates contiguous paged-locked memory, which is mapped write-combined memory, for the DMA buffers. Therefore, the GPU must access DMA buffers by using PCI cycles on computers where AGP transfers that occur outside the AGP aperture are not permitted.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557567">DXGKARG_CREATECONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557618">DXGKARG_PRESENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560975">DXGK_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561037">DXGK_CREATECONTEXTFLAGS</a>



<a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a>



<a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

