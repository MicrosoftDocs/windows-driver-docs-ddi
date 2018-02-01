---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING describes the details of a video decoder downsampling operation.
old-location: display\d3dwddm2_0ddi_video_capability_decoder_downsampling.htm
old-project: display
ms.assetid: 8D12F2AC-2A64-4FEF-813C-15899FBCA108
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING structure [Display Devices], display.d3dwddm2_0ddi_video_capability_decoder_downsampling
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING structure


## -description


<b>D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</b> describes the details of a video decoder downsampling operation.


## -syntax


````
typedef struct D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING {
  const D3D11_1DDI_VIDEO_DECODER_DESC   *pInputDesc;
  D3DDDI_COLOR_SPACE_TYPE               InputColorSpace;
  const D3D11_1DDI_VIDEO_DECODER_CONFIG *pInputConfig;
  const DXGI_RATIONAL                   *pFrameRate;
  const D3D11_1DDI_VIDEO_DECODER_DESC   *pOutputDesc;
  D3DDDI_COLOR_SPACE_TYPE               OutputColorSpace;
  BOOL                                  Supported;
  BOOL                                  RealTime;
} D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING;
````


## -struct-fields




### -field pInputDesc

[in] Contains the decode profile used and the resolution and format of the reference frames.  This is the resolution/format to be downsampled (e.g. 4K, DXGI_FORMAT_P010).


### -field InputColorSpace

[in] Contains the color space information of the reference frame data.


### -field pInputConfig

[in] A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure that contains the configuration data associated with the decode profile .


### -field pFrameRate

[in] Contains the frame rate of the video content.


### -field pOutputDesc

[in] A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that contains the resolution and the format of the display frames.  This is the destination resolution and format of the down sample operation.


<div class="alert"><b>Note</b>  The decode profile (<b>Guid</b>) member of <b>pOutputDesc</b> can be ignored.
</div><div> </div>

### -field OutputColorSpace

[in] Contains the color space information of the display frame data.


### -field Supported

[out] The driver sets this to <b>TRUE</b> if the requested down sampling is supported.  Otherwise, the driver should set this to <b>FALSE</b>.


### -field RealTime

[out] The driver sets this to <b>TRUE</b> if the requested down sampling is supported and the resulting decode operations can occur in real-time.  Otherwise, the driver should set this to <b>FALSE</b>.


## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>

<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

