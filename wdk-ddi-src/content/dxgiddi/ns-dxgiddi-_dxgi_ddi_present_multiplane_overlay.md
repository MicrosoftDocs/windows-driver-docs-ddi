---
UID: NS:dxgiddi._DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY
title: "_DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY" (dxgiddi.h)
description: Specifies overlay planes to display.
old-location: display\dxgi_ddi_present_multiplane_overlay.htm
tech.root: display
ms.assetid: 18811f98-df57-43ab-b8f7-26301abeb823
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY, DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY structure [Display Devices], _DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY, display.dxgi_ddi_present_multiplane_overlay, dxgiddi/DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Dxgiddi.h
api_name:
-	DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY
---

# _DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY structure


## -description


Specifies overlay planes to display.


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.


### -field hResource

A handle to the resource that is displayed by using the overlay plane.


### -field SubResourceIndex

The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or surface, on which an overlay plane is to be displayed.


### -field PlaneAttributes

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh780283">DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES</a>  that specifies overlay plane attributes.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780283">DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES</a>
 

 

