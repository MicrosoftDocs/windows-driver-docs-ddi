---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT
title: PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT (d3d10umddi.h)
description: Queries the number of video decoder configurations that are supported by the display miniport driver for the specified decoder operation.
old-location: display\getvideodecoderconfigcount.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT, PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT callback, d3d10umddi/pfnGetVideoDecoderConfigCount, display.getvideodecoderconfigcount, pfnGetVideoDecoderConfigCount, pfnGetVideoDecoderConfigCount callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT
 - d3d10umddi/PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT
---

# PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT callback function


## -description

Queries the number of video decoder configurations that are supported by the display miniport driver for the specified decoder operation.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*pDecodeDesc* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the video decoder operation.

### -param unnamedParam3

*pConfigCount* [out]

A pointer to a UINT value that specifies the maximum number of decoder configurations that are supported.

## -remarks

The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i>  parameter data is valid before it calls the <b>GetVideoDecoderConfigCount</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a>

