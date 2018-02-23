---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_0021
title: D3D12DDIARG_CREATE_VIDEO_DECODER_0021
author: windows-driver-content
description: Used to create a decoder object for a decode session.
old-location: display\d3d12ddiarg_create_video_decoder.htm
old-project: display
ms.assetid: 8178A279-96FE-40DC-A292-4551FA153F45
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_0021, display.d3d12ddiarg_create_video_decoder, D3D12DDIARG_CREATE_VIDEO_DECODER_0021, D3D12DDIARG_CREATE_VIDEO_DECODER_0021 structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDIARG_CREATE_VIDEO_DECODER_0021
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_0021
---

# D3D12DDIARG_CREATE_VIDEO_DECODER_0021 structure


## -description


Used to create a decoder object for a decode session.


## -syntax


````
typedef struct D3D12DDIARG_CREATE_VIDEO_DECODER_0021 {
  UINT                                     NodeMask;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 Configuration;
  UINT                                     DecodeWidth;
  UINT                                     DecodeHeight;
  UINT                                     MaxDecodePictureBufferCount;
  DXGI_RATIONAL                            FrameRate;
  UINT                                     Bitrate;
  D3D12DDI_VIDEO_USAGE                     Usage;
} D3D12DDIARG_CREATE_VIDEO_DECODER_0021;
````


## -struct-fields




### -field NodeMask

A node mask. For single GPU operation, set this value to zero (0). If there are multiple GPU nodes, set a bit to identify the physical adapter of the device to which the command queue applies. Each bit in the mask corresponds to a single node. Only one  bit may be set.


### -field Configuration

The decode profile and bitstream encryption.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.


### -field DecodeWidth

The decode width of the bitstream to be decoded.


### -field DecodeHeight

The decode height of the bitstream to be decoded.


### -field MaxDecodePictureBufferCount

The maximum number of decode picture buffers this stream can have.


### -field FrameRate

The frame rate of the input video stream.  


### -field BitRate

 


### -field Usage

A hint for the intended usage for the decoder stream. For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_usage.md">D3D12DDI_VIDEO_USAGE</a> enumeration.


#### - Bitrate

The data compression rate, in bits per second, for the compressed video stream.  


## -remarks



Drivers can use the <i>Bitrate</i> and <i>FrameRate</i> parameters to inform heuristics such as intermediate allocation sizes or performance optimizations.  

Decoding a frame is allowed to fail if the <i>Bitrate</i> and <i>FrameRate</i> values are insufficient for the video stream.  If decode fails for this reason, the query <b>D3D12DDI_QUERY_TYPE_VIDEO_DECODE_STATISTICS</b> must return a status of <b>D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED</b>.    

The <i>Bitrate</i> and <i>FrameRate</i> parameters may also be set to zero.  When these values are used, drivers must make worst case assumptions. They are not allowed to fail with <b>D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED</b>.




## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_usage.md">D3D12DDI_VIDEO_USAGE</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDIARG_CREATE_VIDEO_DECODER_0021 structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

