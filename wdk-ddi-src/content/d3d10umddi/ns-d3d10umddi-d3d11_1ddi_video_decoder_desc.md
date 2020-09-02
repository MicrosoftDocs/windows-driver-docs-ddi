---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_DECODER_DESC
title: D3D11_1DDI_VIDEO_DECODER_DESC (d3d10umddi.h)
description: Describes a video stream for a Microsoft Direct3D video decoder or video processor.
old-location: display\d3d11_1ddi_video_decoder_desc.htm
ms.assetid: 35fe914b-13e8-4658-9ea6-af1eb9068f6f
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_DECODER_DESC structure"]
ms.keywords: D3D11_1DDI_VIDEO_DECODER_DESC, D3D11_1DDI_VIDEO_DECODER_DESC structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_DECODER_DESC, display.d3d11_1ddi_video_decoder_desc
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_DECODER_DESC
f1_keywords:
 - D3D11_1DDI_VIDEO_DECODER_DESC
 - d3d10umddi/D3D11_1DDI_VIDEO_DECODER_DESC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3D11_1DDI_VIDEO_DECODER_DESC
---

# D3D11_1DDI_VIDEO_DECODER_DESC structure


## -description

Describes a video stream for a Microsoft Direct3D video decoder or video processor.

## -struct-fields

### -field Guid

The DXVA decoding profile. To get the list of profiles supported by the device, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofile">GetVideoDecoderProfile</a> function.

### -field SampleWidth

The width of the video frame, in pixels.

### -field SampleHeight

The height of the video frame, in pixels.

### -field OutputFormat

The output surface format, specified as a <b>DXGI_FORMAT</b> value. The <b>DXGI_FORMAT</b> enumeration is defined in Dxgiformat.h.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderprofile">GetVideoDecoderProfile</a>

