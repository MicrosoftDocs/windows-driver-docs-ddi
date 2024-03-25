---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES
title: PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES (d3d10umddi.h)
description: Queries the driver for video capabilities. Required for Windows Display Driver Model (WDDM) 2.0 or later drivers.
ms.date: 12/09/2022
keywords: ["PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES callback function"]
ms.keywords: PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES, PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES callback, d3d10umddi/pfnQueryVideoCapabilities, display.queryvideocapabilities, pfnQueryVideoCapabilities, pfnQueryVideoCapabilities callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES
 - d3d10umddi/PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES
---

# PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES callback function

## -description

**PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES** queries the driver for its video capabilities. WDDM 2.0 or later drivers must implement this function.

## -parameters

### -param hDevice

[in] A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the **hDevice** member of the [**D3DDDIARG_CREATEDEVICE**](../d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice.md) structure at device creation.

### -param QueryType

[in] A [**D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY**](ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md) value that indicates the type of data being queried.

### -param DataSize

[in] Size in bytes of the data that **pData** points to. This value is dependent on the **QueryType** member. For example, if **QueryType** is D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS, set **DataSize** to ```sizeof(D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS)```.

### -param pData

[in/out] Pointer to a structure containing both caller-provided input parameters and output parameters that are to be filled in by the driver. The type of structure depends on the value of **QueryType**.

| Value of QueryType | Structure that pData points to |
| ------------------ | ------------------------------ |
| D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING | [**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling.md) |
| D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING | [**D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.md) |
| D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS | [**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_caps.md) |
| D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT | [**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsample_output_format.md) |
| D3DWDDM2_4DDI_VIDEO_CAPABILITY_QUERY_DECODER_HISTOGRAM | [**D3DWDDM2_4DDI_VIDEO_CAPABILITY_DECODER_HISTOGRAM**](ns-d3d10umddi-d3dwddm2_4ddi_video_capability_decoder_histogram.md) |

## -see-also

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_caps.md)

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsample_output_format.md)

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling.md)

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY**](ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md)

[**D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING**](ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.md)
