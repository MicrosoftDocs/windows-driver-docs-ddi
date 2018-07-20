---
UID: NS:d3dkmddi._DXGK_ALLOCATIONLIST
title: "_DXGK_ALLOCATIONLIST"
author: windows-driver-content
description: The DXGK_ALLOCATIONLIST structure describes an allocation specification that is used in direct memory access (DMA) buffering.
old-location: display\dxgk_allocationlist.htm
tech.root: display
ms.assetid: 1be057dc-6a97-4798-a152-7cc6d6febda5
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_ALLOCATIONLIST, DXGK_ALLOCATIONLIST structure [Display Devices], DmStructs_ed92f9cf-ad3f-4566-89ff-31d6b162f755.xml, _DXGK_ALLOCATIONLIST, d3dkmddi/DXGK_ALLOCATIONLIST, display.dxgk_allocationlist
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
-	DXGK_ALLOCATIONLIST
product:
- Windows
targetos: Windows
req.typenames: DXGK_ALLOCATIONLIST
---

# _DXGK_ALLOCATIONLIST structure


## -description


The <b>DXGK_ALLOCATIONLIST</b> structure describes an allocation specification that is used in direct memory access (DMA) buffering.


## -struct-fields




### -field hDeviceSpecificAllocation

[in/out] An open handle to the allocation that is being referenced (that is, the handle that the driver returned in the <b>hDeviceSpecificAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561983">DXGK_OPENALLOCATIONINFO</a> structure for the allocation in a call to the driver's <a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a> function).


### -field WriteOperation

 


### -field SegmentId

 


### -field Reserved

 


### -field VirtualAddress

[in/out] A <b>D3DGPU_VIRTUAL_ADDRESS</b> data type that indicates the virtual address.

Supported starting with Windows 10.


### -field PhysicalAddress

[in/out] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address, within the segment that <b>SegmentId</b> specifies, where the allocation was last paged-in at. This member is set to zero if no pre-patching information is available.

Supported starting with Windows 10.

[in/out] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address, within the segment that <b>SegmentId</b> specifies, where the allocation was last paged-in at. This member is set to zero if no pre-patching information is available.


#### - ( unnamed struct )

Â 



#### WriteOperation

[in/out] A member in the structure that <b>DXGK_ALLOCATIONLIST</b> contains that can hold information about whether the allocation can be written to. Setting this member to 1 indicates that the allocation can be written to anywhere in the DMA buffer.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001). 



#### SegmentId

[in/out] A member in the structure that <b>DXGK_ALLOCATIONLIST</b> contains that can hold information about the identifier of a segment that the allocation was last paged in at. Setting this member to 0 indicates that no pre-patching information is available.

Setting this member is equivalent to setting the second through sixth bit of a 32-bit value (0x0000002E). 



#### Reserved

[in] A member in the structure that <b>DXGK_ALLOCATIONLIST</b> contains that is reserved. This member should be set to 0.

Setting this member is equivalent to setting the remaining 26 bits (0xFFFFFFC0) of a 32-bit value to zeros. 


## -remarks



In the display miniport driver's <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> function, the driver generates a list of <b>DXGK_ALLOCATIONLIST</b> structures for allocation specifications that will be used in a direct memory access (DMA) buffer. The video memory manager uses the list to split and patch DMA buffers appropriately. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561983">DXGK_OPENALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/551154d7-950d-40e5-810b-8d803c1731ca">DxgkDdiOpenAllocation</a>



<a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a>
 

 

