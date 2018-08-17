---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE
title: "_DXGK_MULTIPLANE_OVERLAY_PLANE"
author: windows-driver-content
description: Specifies an overlay plane to display in a call to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay function.
old-location: display\dxgk_multiplane_overlay_plane.htm
ms.assetid: 8ea1abc7-b861-4217-a3ab-cf60026d9608
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE, DXGK_MULTIPLANE_OVERLAY_PLANE structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE, display.dxgk_multiplane_overlay_plane
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	D3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_PLANE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE structure


## -description


Specifies an overlay plane to display in a call to the <a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.

If <b>FALSE</b>, the display miniport driver should disable the specified overlay plane.

If a plane was enabled during a previous call to <a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>, the driver should continue to display the plane without flipping it.


### -field AllocationSegment

[in] The identifier of a segment that data is read from.


### -field AllocationAddress

[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address, within the segment that <b>AllocationSegment</b> specifies, where the data is read.


### -field hAllocation

A handle to the allocation to be displayed on the overlay plane.


### -field PlaneAttributes

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh780301">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>  that specifies overlay plane attributes.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780301">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>
 

 

