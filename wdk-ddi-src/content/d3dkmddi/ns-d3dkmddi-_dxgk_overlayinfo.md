---
UID: NS:d3dkmddi._DXGK_OVERLAYINFO
title: "_DXGK_OVERLAYINFO"
author: windows-driver-content
description: The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay.
old-location: display\dxgk_overlayinfo.htm
old-project: display
ms.assetid: 7c2a7484-452f-4801-b650-3d8221740892
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGK_OVERLAYINFO, DXGK_OVERLAYINFO structure [Display Devices], DmStructs_232178f2-9a25-40aa-8604-0414128c1a91.xml, _DXGK_OVERLAYINFO, d3dkmddi/DXGK_OVERLAYINFO, display.dxgk_overlayinfo
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_OVERLAYINFO
product: Windows
targetos: Windows
req.typenames: DXGK_OVERLAYINFO
---

# _DXGK_OVERLAYINFO structure


## -description


The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay. 


## -syntax


````
typedef struct _DXGK_OVERLAYINFO {
  HANDLE           hAllocation;
  PHYSICAL_ADDRESS PhysicalAddress;
  UINT             SegmentId;
  RECT             DstRect;
  RECT             SrcRect;
  VOID             *pPrivateDriverData;
  UINT             PrivateDriverDataSize;
} DXGK_OVERLAYINFO;
````


## -struct-fields




### -field hAllocation

[in] A handle to the allocation to be displayed on the overlay.


### -field PhysicalAddress

[in] The physical address, within the segment that <b>SegmentId</b> specifies, of the allocation to be displayed.


### -field SegmentId

[in] The identifier of a segment in which the allocation is currently paged-in.


### -field DstRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that contains the overlay destination rectangle, in device coordinates.


### -field SrcRect

[in] A RECT structure that contains the overlay source rectangle, in device coordinates.


### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateoverlay.md">DxgkDdiUpdateOverlay</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createoverlay.md">DXGKARG_CREATEOVERLAY</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_updateoverlay.md">DXGKARG_UPDATEOVERLAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_OVERLAYINFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

