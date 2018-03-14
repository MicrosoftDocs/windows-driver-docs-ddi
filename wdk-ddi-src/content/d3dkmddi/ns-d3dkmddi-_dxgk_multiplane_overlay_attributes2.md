---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2
title: "_DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2"
author: windows-driver-content
description: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 is used by the display miniport driver to specify overlay plane attributes.
old-location: display\dxgk_multiplane_overlay_attributes2.htm
old-project: display
ms.assetid: 48C481EF-F3A1-48BF-B251-86D06AC125CC
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2
---

# _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 structure


## -description


<b>DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</b> is used by the display miniport driver to specify overlay plane attributes.



## -syntax


````
typedef struct _DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 {
  DXGK_MULTIPLANE_OVERLAY_FLAGS              Flags;
  RECT                                       SrcRect;
  RECT                                       DstRect;
  RECT                                       ClipRect;
  D3DDDI_ROTATION                            Rotation;
  DXGK_MULTIPLANE_OVERLAY_BLEND              Blend;
  DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT VideoFrameFormat;
  D3DDDI_COLOR_SPACE_TYPE                    ColorSpaceType;
  DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT      StereoFormat;
  BOOL                                       StereoLeftViewFrame0;
  BOOL                                       StereoBaseViewFrame0;
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE   StereoFlipMode;
  DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY    StretchQuality;
  UINT                                       ColorKey;
} DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2;
````


## -struct-fields




### -field Flags

Specifies a combination of flip operations by performing a bitwise OR operation on the values in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_flags.md">DXGK_MULTIPLANE_OVERLAY_FLAGS</a> enumeration.


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

Specifies the clockwise rotation of the overlay plane, given as a value from the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a> enumeration.


### -field Blend

Specifies the blend mode that applies to this overlay plane and the plane beneath it, given as a value from the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_blend.md">DXGK_MULTIPLANE_OVERLAY_BLEND</a> enumeration.


### -field VideoFrameFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_video_frame_format.md">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a> enumeration.


### -field ColorSpaceType

Specifies the colorspace configuration, given as a value from the <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a> enumeration.


### -field StereoFormat

Specifies the overlay plane's video frame format, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_format.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a> enumeration.


### -field StereoLeftViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoBaseViewFrame0

Reserved for system use. Must always be <b>FALSE</b>.


### -field StereoFlipMode

Specifies the overlay plane's stereo flip mode, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_flip_mode.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a> enumeration.


### -field StretchQuality

Specifies the overlay plane's stretch quality, given as a value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality.md">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a> enumeration.


### -field Reserved1

 




#### - ColorKey

Specifies the color key value used when color key blending is enabled for legacy overlays.


## -see-also

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_format.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FORMAT</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stretch_quality.md">DXGK_MULTIPLANE_OVERLAY_STRETCH_QUALITY</a>



<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_blend.md">DXGK_MULTIPLANE_OVERLAY_BLEND</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_video_frame_format.md">DXGK_MULTIPLANE_OVERLAY_VIDEO_FRAME_FORMAT</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_multiplane_overlay_stereo_flip_mode.md">DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_flags.md">DXGK_MULTIPLANE_OVERLAY_FLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

