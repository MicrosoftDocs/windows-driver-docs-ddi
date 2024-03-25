---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GETCAPS
title: PFND3D12DDI_VIDEO_GETCAPS (d3d12umddi.h)
description: The pfnGetCaps callback function defines an entry point for video specific caps.
old-location: display\pfnd3d12ddi_video_getcaps.htm
ms.date: 02/16/2022
keywords: ["PFND3D12DDI_VIDEO_GETCAPS callback function"]
ms.keywords: PFND3D12DDI_VIDEO_GETCAPS, PFND3D12DDI_VIDEO_GETCAPS callback, d3d12umddi/pfnGetCaps, display.pfnd3d12ddi_video_getcaps, pfnGetCaps, pfnGetCaps callback function [Display Devices]
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
 - PFND3D12DDI_VIDEO_GETCAPS
 - d3d12umddi/PFND3D12DDI_VIDEO_GETCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_VIDEO_GETCAPS
---

# PFND3D12DDI_VIDEO_GETCAPS callback function

## -description

The D3D runtime calls a client driver's **PFND3D12DDI_VIDEO_GETCAPS** callback function to query for video-related support provided by the driver for a specified type.

## -parameters

### -param hDrvDevice [in]

The handle of a device.

### -param pArgs [in, out]

Pointer to a caller-allocated [**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md) structure used to request a video-specific capability.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

The following table provides a few examples of the meaning/values of **pData** and **DataSize** for various **D3D12DDICAPS_TYPE_VIDEO_0020** values. Note that **pInfo** points to NULL in all of these examples, so is not shown in the table.

| D3D12DDICAPS_TYPE_*XXX*  | pData | DataSize |
| -----------------------  | ----- | -------- |
| *VIDEO_0020_DECODE_SUPPORT*   | D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 *  | sizeof(D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020)  |
| *VIDEO_0020_DECODE_PROFILES*  | D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020 * | sizeof(D3D12DDI_VIDEO_DECODE_PROFILES_DATA_0020) |
| *VIDEO_0020_PROCESS_SUPPORT*  | D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 * | sizeof(D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032) |
| *VIDEO_0032_DECODER_HEAP_SIZE*    | D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072 * | sizeof(D3D12DDI_VIDEO_DECODER_HEAP_SIZE_DATA_0072) |
| *VIDEO_0053_MOTION_ESTIMATOR* | D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053 * | sizeof(D3D12DDI_VIDEO_MOTION_ESTIMATOR_DATA_0053) |
| *VIDEO_0080_ENCODER_CODEC* | D3D12DDICAPS_VIDEO_ENCODER_CODEC_DATA_0080 | sizeof(D3D12DDICAPS_VIDEO_ENCODER_CODEC_DATA_0080) |

## -see-also

[**D3D12DDIARG_VIDEO_GETCAPS_0020**](ns-d3d12umddi-d3d12ddiarg_video_getcaps_0020.md)

[**PFND3D12DDI_FILLDDITTABLE**](nc-d3d12umddi-pfnd3d12ddi_fillddittable.md)
