---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERCONFIG
title: PFND3D11_1DDI_GETVIDEODECODERCONFIG (d3d10umddi.h)
description: Queries the video decoder configuration for a specified video operation.
old-location: display\getvideodecoderconfig.htm
ms.assetid: e13cb42b-258e-4fa6-8dc0-8983b118af3c
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEODECODERCONFIG callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERCONFIG, PFND3D11_1DDI_GETVIDEODECODERCONFIG callback, d3d10umddi/pfnGetVideoDecoderConfig, display.getvideodecoderconfig, pfnGetVideoDecoderConfig, pfnGetVideoDecoderConfig callback function [Display Devices]
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
 - PFND3D11_1DDI_GETVIDEODECODERCONFIG
 - d3d10umddi/PFND3D11_1DDI_GETVIDEODECODERCONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnGetVideoDecoderConfig
---

# PFND3D11_1DDI_GETVIDEODECODERCONFIG callback function


## -description

Queries the video decoder configuration for a specified video operation.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDecodeDesc* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the video decoder operation.

### -param Arg3

*Index* [in]

The zero-based index of the video decoder configuration that is used for the specified operation. The display miniport driver specifies the maximum number of video decoder configurations that are required for the operation through a call to its <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfigcount">GetVideoDecoderConfigCount</a> function.

### -param Arg4

*pConfig* [out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_config">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure that describes the video decoder configuration.

## -remarks

The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i> and <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderConfig</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_config">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderconfigcount">GetVideoDecoderConfigCount</a>