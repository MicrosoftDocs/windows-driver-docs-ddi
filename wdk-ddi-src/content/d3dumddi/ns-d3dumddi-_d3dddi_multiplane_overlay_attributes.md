---
UID: NS:d3dumddi._D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
title: _D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES (d3dumddi.h)
description: Used by the user-mode display driver to specify overlay plane attributes.
old-location: display\d3dddi_multiplane_overlay_attributes.htm
tech.root: display
ms.assetid: 6f758785-5d7f-4d63-82c7-93ced5de3da4
ms.date: 05/10/2018
keywords: ["D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES structure"]
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES, D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES structure [Display Devices], _D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES, display.d3dddi_multiplane_overlay_attributes
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
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
f1_keywords:
 - _D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
 - d3dumddi/_D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
 - D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
 - d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dumddi.h
api_name:
 - D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES
---

# _D3DDDI_MULTIPLANE_OVERLAY_ATTRIBUTES structure


## -description

Used by the user-mode display driver to specify overlay plane attributes.

## -struct-fields

### -field Flags

Specifies a flip operation as one of the applicable values in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddi_multiplane_overlay_flags">D3DDDI_MULTIPLANE_OVERLAY_FLAGS</a> enumeration.

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

Specifies the blend mode that applies to this overlay plane and the plane beneath it, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddi_multiplane_overlay_blend">D3DDDI_MULTIPLANE_OVERLAY_BLEND</a> enumeration.

### -field DirtyRectCount

The number of dirty rectangles specified for the overlay plane. If zero, the entire plane is considered dirty.

### -field pDirtyRects

A pointer to an array of dirty rectangles (<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>s), relative to the source rectangle <b>SrcRect</b>, that indicate the portion of the overlay plane that has changed.

The driver can use this member to perform optimizations, though it's not required to use the dirty rectangle info. However, the driver should never fail a function call based on the provided dirty rectangles.

### -field NumFilters

Optionally specifies the number of filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.

### -field pFilters

An optional pointer to a buffer that specifies the filters that the driver and hardware implement on the overlay plane. Note that the operating system ignores this member.

### -field VideoFrameFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_multiplane_overlay_video_frame_format">D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a> enumeration.

<div class="alert"><b>Note</b>  This value must always be <b>DXGI_DDI_MULIIPLANE_OVERLAY_VIDEO_FRAME_FORMAT_PROGRESSIVE</b>. The operating system does not support the other enumeration values.</div>
<div> </div>

### -field YCbCrFlags

Specifies YUV range and conversion info given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_multiplane_overlay_ycbcr_flags">D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a> enumeration.

### -field StretchQuality

Specifies the overlay plane's stretch quality, given as a value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_multiplane_overlay_stretch_quality">D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a> enumeration.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddi_multiplane_overlay_blend">D3DDDI_MULTIPLANE_OVERLAY_BLEND</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-_d3dddi_multiplane_overlay_flags">D3DDDI_MULTIPLANE_OVERLAY_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_multiplane_overlay_stretch_quality">D3DDDI_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_multiplane_overlay_video_frame_format">D3DDDI_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ne-d3dumddi-d3dddi_multiplane_overlay_ycbcr_flags">D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>

