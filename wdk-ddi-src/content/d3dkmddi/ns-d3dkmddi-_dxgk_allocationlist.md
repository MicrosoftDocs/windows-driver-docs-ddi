---
UID: NS:d3dkmddi._DXGK_ALLOCATIONLIST
title: "_DXGK_ALLOCATIONLIST"
author: windows-driver-content
description: The DXGK_ALLOCATIONLIST structure describes an allocation specification that is used in direct memory access (DMA) buffering.
old-location: display\dxgk_allocationlist.htm
old-project: display
ms.assetid: 1be057dc-6a97-4798-a152-7cc6d6febda5
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_DXGK_ALLOCATIONLIST, DmStructs_ed92f9cf-ad3f-4566-89ff-31d6b162f755.xml, display.dxgk_allocationlist, d3dkmddi/DXGK_ALLOCATIONLIST, DXGK_ALLOCATIONLIST structure [Display Devices], DXGK_ALLOCATIONLIST"
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_ALLOCATIONLIST
product: Windows
targetos: Windows
req.typenames: DXGK_ALLOCATIONLIST
---

# _DXGK_ALLOCATIONLIST structure


## -description


The <b>DXGK_ALLOCATIONLIST</b> structure describes an allocation specification that is used in direct memory access (DMA) buffering.


## -syntax


````
typedef struct _DXGK_ALLOCATIONLIST {
  HANDLE           hDeviceSpecificAllocation;
  struct {
    UINT WriteOperation  :1;
    UINT SegmentId  :5;
    UINT Reserved  :26;
  };
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  union {
    PHYSICAL_ADDRESS       PhysicalAddress;
    D3DGPU_VIRTUAL_ADDRESS VirtualAddress;
  };
#else 
  PHYSICAL_ADDRESS PhysicalAddress;
#endif 
} DXGK_ALLOCATIONLIST;
````


## -struct-fields




### -field hDeviceSpecificAllocation

[in/out] An open handle to the allocation that is being referenced (that is, the handle that the driver returned in the <b>hDeviceSpecificAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_openallocationinfo.md">DXGK_OPENALLOCATIONINFO</a> structure for the allocation in a call to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a> function).


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


#### - VirtualAddress

[in/out] A <b>D3DGPU_VIRTUAL_ADDRESS</b> data type that indicates the virtual address.

Supported starting with Windows 10.


## -remarks



In the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> function, the driver generates a list of <b>DXGK_ALLOCATIONLIST</b> structures for allocation specifications that will be used in a direct memory access (DMA) buffer. The video memory manager uses the list to split and patch DMA buffers appropriately. 




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_openallocationinfo.md">DXGK_OPENALLOCATIONINFO</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_ALLOCATIONLIST structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

