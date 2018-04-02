---
UID: NS:d3dumddi._D3DDDI_PRESENT_MULTIPLANE_OVERLAY
title: "_D3DDDI_PRESENT_MULTIPLANE_OVERLAY"
author: windows-driver-content
description: Specifies an overlay plane to display.
old-location: display\d3dddi_present_multiplane_overlay.htm
old-project: display
ms.assetid: 45db9dbb-d1e1-4ed3-bf4d-99b6ac7542ae
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_PRESENT_MULTIPLANE_OVERLAY, D3DDDI_PRESENT_MULTIPLANE_OVERLAY structure [Display Devices], _D3DDDI_PRESENT_MULTIPLANE_OVERLAY, d3dumddi/D3DDDI_PRESENT_MULTIPLANE_OVERLAY, display.d3dddi_present_multiplane_overlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	D3dumddi.h
api_name:
-	D3DDDI_PRESENT_MULTIPLANE_OVERLAY
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_PRESENT_MULTIPLANE_OVERLAY
---

# _D3DDDI_PRESENT_MULTIPLANE_OVERLAY structure


## -description


Specifies an overlay plane to display.


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates if the overlay plane specified by <b>LayerIndex</b> is enabled for display.


### -field hResource

A handle to the resource that is displayed by using the overlay plane.


### -field SubResourceIndex

The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or surface, on which an overlay plane is to be displayed.


### -field PlaneAttributes

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh780234">D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780234">D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES</a>
 

 

