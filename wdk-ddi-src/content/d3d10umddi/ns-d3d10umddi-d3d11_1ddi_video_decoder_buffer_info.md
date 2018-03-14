---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO
title: D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO
author: windows-driver-content
description: Specifies information about a video decoder buffer.
old-location: display\d3d11_1ddi_video_decoder_buffer_info.htm
old-project: display
ms.assetid: 1f013077-ea85-4c35-8667-cdf0c1353b0f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO, D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO, display.d3d11_1ddi_video_decoder_buffer_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO
---

# D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO structure


## -description


Specifies information about a video decoder buffer.


## -syntax


````
typedef struct D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO {
  D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE Type;
  UINT                                 Size;
  UINT                                 Usage;
} D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO;
````


## -struct-fields




### -field Type

The type of buffer, specified as a constant value of the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> enumeration.

In D3d10umddi.h, <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a> and <b>D3D11_1DDI_VIDEO_DECODER_BUFFER_TYPE</b> are defined as the same type.


### -field Size

The size of the buffer, in bytes.


### -field Usage

A value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_usage.md">D3D11_1DDI_VIDEO_USAGE</a> enumeration that identifies how the decode device plays video.


## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_usage.md">D3D11_1DDI_VIDEO_USAGE</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_ddi_video_decoder_buffer_type.md">D3D11_DDI_VIDEO_DECODER_BUFFER_TYPE</a>



 

 


