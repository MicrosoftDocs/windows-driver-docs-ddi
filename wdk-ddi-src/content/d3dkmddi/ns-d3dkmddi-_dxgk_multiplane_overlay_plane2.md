---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE2
title: "_DXGK_MULTIPLANE_OVERLAY_PLANE2"
author: windows-driver-content
description: DXGK_MULTIPLANE_OVERLAY_PLANE2 is used with the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 function to specify an overlay plane to display.
old-location: display\dxgk_multiplane_overlay_plane2.htm
old-project: display
ms.assetid: 31A1EAFB-FA48-432D-963E-EA907B43F08A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE2, DXGK_MULTIPLANE_OVERLAY_PLANE2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE2, display.dxgk_multiplane_overlay_plane2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	DXGK_MULTIPLANE_OVERLAY_PLANE2
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE2
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE2 structure


## -description


<b>DXGK_MULTIPLANE_OVERLAY_PLANE2</b> is used with the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</a> function to specify an overlay plane to display.


## -syntax


````
typedef struct _DXGK_MULTIPLANE_OVERLAY_PLANE2 {
  UINT                                LayerIndex;
  BOOL                                Enabled;
  UINT                                AllocationSegment;
  PHYSICAL_ADDRESS                    AllocationAddress;
  HANDLE                              hAllocation;
  DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 PlaneAttributes;
} DXGK_MULTIPLANE_OVERLAY_PLANE2;
````


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.


### -field AllocationSegment

The identifier of a segment that data is read from.


### -field AllocationAddress

A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address within the segment that <b>AllocationSegment</b> specifies, where the data is read.


### -field hAllocation

A handle to the allocation to be displayed on the overlay plane.


### -field PlaneAttributes

A structure of type <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a> that specifies overlay plane attributes.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MULTIPLANE_OVERLAY_PLANE2 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

