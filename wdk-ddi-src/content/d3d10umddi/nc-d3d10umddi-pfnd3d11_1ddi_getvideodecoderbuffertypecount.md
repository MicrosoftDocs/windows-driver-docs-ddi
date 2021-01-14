---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT
title: PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT (d3d10umddi.h)
description: Queries the number of buffer types that the display miniport driver requires to perform a specified decode operation.
old-location: display\getvideodecoderbuffertypecount.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT, PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT callback, d3d10umddi/pfnGetVideoDecoderBufferTypeCount, display.getvideodecoderbuffertypecount, pfnGetVideoDecoderBufferTypeCount, pfnGetVideoDecoderBufferTypeCount callback function [Display Devices]
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
 - PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT
 - d3d10umddi/PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT
---

# PFND3D11_1DDI_GETVIDEODECODERBUFFERTYPECOUNT callback function


## -description

Queries the number of buffer types that the display miniport driver requires to perform a specified decode operation.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDecodeDesc* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that specifies the video decoder operation.

### -param Arg3

*pBufferTypeCount* [out]

A pointer to a UINT value that specifies the maximum number of buffer types that the driver supports for the specified video decoder operation.

## -remarks

The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i>  parameter data is valid before it calls the <b>GetVideoDecoderBufferTypeCount</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_decoder_desc">D3D11_1DDI_VIDEO_DECODER_DESC</a>

