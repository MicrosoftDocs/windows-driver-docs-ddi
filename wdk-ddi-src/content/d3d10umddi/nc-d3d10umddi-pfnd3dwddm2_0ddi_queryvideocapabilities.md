---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES
title: PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES (d3d10umddi.h)
description: Queries the driver for video capabilities. Required for Windows Display Driver Model (WDDM) 2.0 or later drivers.
old-location: display\queryvideocapabilities.htm
ms.assetid: C86C7D1C-541F-4EC3-B4C8-126826BE3529
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES, PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES callback, d3d10umddi/pfnQueryVideoCapabilities, display.queryvideocapabilities, pfnQueryVideoCapabilities, pfnQueryVideoCapabilities callback function [Display Devices]
ms.topic: callback
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
 - "d3d10umddi/pfnQueryVideoCapabilities"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnQueryVideoCapabilities
product:
 - Windows
---

# PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES callback function

## -description

Queries the driver for video capabilities. Required for Windows Display Driver Model (WDDM) 2.0 or later drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param QueryType

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query">D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY</a> value indicating the type of data being queried.

### -param DataSize

Specifies the size of the <b>pData</b> member. This is dependent on the <b>QueryType</b> member.

### -param pData

Pointer to a structure containing data further identifying input parameters and output parameters to be filled in by the driver. The following structures are supported for the following query types:

*pData.D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS*

<b>pData</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm2_0ddi_video_decoder_caps">D3DWDDM2_0DDI_VIDEO_DECODER_CAPS</a> structure.


*pData.D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING*

<b>pData</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a> structure.


*pData.D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMENDED_DECODER_DOWNSAMPLING*

<b>pData</b> points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query">D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3dwddm2_0ddi_video_decoder_caps">D3DWDDM2_0DDI_VIDEO_DECODER_CAPS</a>

