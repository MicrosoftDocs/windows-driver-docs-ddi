---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS
author: windows-driver-content
description: Specifies video processor-specific capabilities.
old-location: display\d3d11_1ddi_video_processor_conversion_caps.htm
old-project: display
ms.assetid: 571a90a8-a32d-44a5-af5f-e2b9e2692945
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS
req.alt-loc: D3d10umddi.h
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS enumeration



## -description
Specifies video processor-specific capabilities.



## -syntax

````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_BLEND                = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_BOB                  = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_ADAPTIVE             = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_MOTION_COMPENSATION  = 0x8,
  D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_INVERSE_TELECINE                 = 0x10,
  D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_FRAME_RATE_CONVERSION            = 0x20
} D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS;
````


## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_BLEND

The driver can perform blend deinterlacing where the two fields in an interlaced frame are blended. The driver uses this deinterlacing type when it deinterlaces at half rate. For more information about half rate, see <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_output_rate.md">DXVAHDDDI_OUTPUT_RATE</a>.


### -field D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_BOB

The driver can perform Bob deinterlacing where missing scan lines are created from the lines above and below the missing line. The 4tap filter ([â€“1,9,9,â€“1]/16) produces slightly better results. The driver uses this deinterlacing type when not enough reference frames are provided for adaptive deinterlacing.


### -field D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_ADAPTIVE

The driver can perform adaptive deinterlacing where missing scan lines are created from either spatial or temporal interpolation by switching between the two interpolation types, depending on the pixel or field motion.


### -field D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_DEINTERLACE_MOTION_COMPENSATION

The driver can perform motion-compensated deinterlacing where missing scan lines are created by using the motion vectors. This deinterlacing type is the most advanced deinterlacing that is implemented by using a proprietary algorithm.


### -field D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_INVERSE_TELECINE

The driver can convert from the interlaced frames to original progressive frames by reversing the telecine. For more information about reversing the telecine, see the <b>ITelecineCaps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_rate_conversion_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a> structure.


### -field D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS_FRAME_RATE_CONVERSION

The driver can convert the frame rate by interpolating the frames.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_rate_conversion_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_output_rate.md">DXVAHDDDI_OUTPUT_RATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

