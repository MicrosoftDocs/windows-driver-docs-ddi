---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2
title: "_DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2"
author: windows-driver-content
description: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 is used by the display miniport driver to specify overlay plane attributes.
old-location: display\dxgk_multiplane_overlay_attributes2.htm
ms.assetid: 48C481EF-F3A1-48BF-B251-86D06AC125CC
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2, DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2, display.dxgk_multiplane_overlay_attributes2
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2
---

# _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 structure


## -description


<b>DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</b> is used by the display miniport driver to specify overlay plane attributes.



## -struct-fields




### -field Flags

Specifies a combination of flip operations by performing a bitwise OR operation on the values in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780304">DXGK_MULTIPLANE_OVERLAY_FLAGS</a> enumeration.


### -field SrcRect

Specifies the source rectangle relative to the source resource.


### -field DstRect

Specifies the destination rectangle relative to the monitor resolution.


### -field ClipRect

Specifies any additional clipping region relative to <b>DstRect</b> 
                                                            after the data has been stretched according to the values of <b>SrcRect</b> and <b>DstRect</b>.

The driver and hardware can use the <b>ClipRect</b> member to apply a common stretch factor 
                                                            as the clipping changes when an application occludes part of the <b>DstRect</b> destination rectangle.


### -field Rotation

Specifies the clockwise rotation of the overlay plane, given as a value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a> enumeration.


### -field Blend

Specifies the blend mode that applies to this overlay plane and the plane beneath it, given as a value from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780302">DXGK_MULTIPLANE_OVERLAY_BLEND</a> enumeration.


### -field VideoFrameFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780308">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a> enumeration.


### -field ColorSpaceType

Specifies the color space configuration, given as a value from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a> enumeration.


### -field StereoFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780307">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a> enumeration.


### -field StereoLeftViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoBaseViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoFlipMode

Specifies the overlay plane's stereo flip mode, given as a value from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780306">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a> enumeration.


### -field StretchQuality

Specifies the overlay plane's stretch quality, given as a value from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn305134">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a> enumeration.


### -field Reserved1

*ColorKey*

Specifies the color key value used when color key blending is enabled for legacy overlays.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544646">D3DDDI_ROTATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780302">DXGK_MULTIPLANE_OVERLAY_BLEND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780304">DXGK_MULTIPLANE_OVERLAY_FLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780306">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780307">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn305134">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780308">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a>
 

 

