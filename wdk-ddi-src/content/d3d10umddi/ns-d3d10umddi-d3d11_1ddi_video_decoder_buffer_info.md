---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO
title: D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO
author: windows-driver-content
description: Specifies information about a video decoder buffer.
old-location: display\d3d11_1ddi_video_decoder_buffer_info.htm
old-project: display
ms.assetid: 1f013077-ea85-4c35-8667-cdf0c1353b0f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO structure [Display Devices], display.d3d11_1ddi_video_decoder_buffer_info, D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO, d3d10umddi/D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

