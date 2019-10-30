---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES
title: _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES (d3dkmddi.h)
description: Used by the display miniport driver to specify overlay plane attributes.
old-location: display\dxgk_multiplane_overlay_attributes.htm
ms.assetid: 1f48a08f-138c-44b4-b13f-efa9b448ce4f
ms.date: 05/10/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES, DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES, display.dxgk_multiplane_overlay_attributes
ms.topic: struct
f1_keywords:
 - "d3dkmddi/DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES
---

# _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES structure


## -description


Used by the display miniport driver to specify overlay plane attributes.


## -struct-fields




### -field Flags

Specifies a flip operation as one of the applicable constant values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_flags">DXGK_MULTIPLANE_OVERLAY_FLAGS</a> enumeration.


### -field SrcRect

Specifies the source rectangle, of type <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>, relative to the source resource.


### -field DstRect

Specifies the destination rectangle, of type <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>, relative to the monitor resolution.


### -field ClipRect

Specifies any additional clipping, of type <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>, relative to the <b>DstRect</b> rectangle, after the data has been stretched according to the values of <b>SrcRect</b> and <b>DstRect</b>.

The driver and hardware can use the <b>ClipRect</b> member to apply a common stretch factor as the clipping changes when an app occludes part of the <b>DstRect</b> destination rectangle.


### -field Rotation

Specifies the clockwise rotation of the overlay plane, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a> enumeration.


### -field Blend

Specifies the blend mode that applies to this overlay plane and the plane beneath it, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_blend">DXGK_MULTIPLANE_OVERLAY_BLEND</a> enumeration.


### -field NumFilters

Optionally specifies the number of filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.


### -field pFilters

An optional pointer to a buffer that specifies the filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.


### -field VideoFrameFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_video_frame_format">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a> enumeration.

<div class="alert"><b>Note</b>  This value must always be <b>DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b>. The operating system does not support the other enumeration values.</div>
<div> </div>

### -field YCbCrFlags

Specifies YUV range and conversion info given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_ycbcr_flags">DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a> enumeration.


### -field StereoFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_format">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a> enumeration.

<div class="alert"><b>Note</b>  This value must always be <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT_MONO</b>. The operating system does not support the other enumeration values.</div>
<div> </div>

### -field StereoLeftViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoBaseViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoFlipMode

Specifies the overlay plane's stereo flip mode, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_flip_mode">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a> enumeration.

<div class="alert"><b>Note</b>  This value must always be <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</b>. The operating system does not support the other enumeration values.</div>
<div> </div>

### -field StretchQuality

Specifies the overlay plane's stretch quality, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a> enumeration.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_blend">DXGK_MULTIPLANE_OVERLAY_BLEND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_flags">DXGK_MULTIPLANE_OVERLAY_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_flip_mode">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_format">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_multiplane_overlay_video_frame_format">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_ycbcr_flags">DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a>
 

 

