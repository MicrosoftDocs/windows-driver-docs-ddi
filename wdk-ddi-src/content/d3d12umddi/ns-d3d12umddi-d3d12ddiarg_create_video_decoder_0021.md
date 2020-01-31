---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_DECODER_0021
title: D3D12DDIARG_CREATE_VIDEO_DECODER_0021 (d3d12umddi.h)
description: Used to create a decoder object for a decode session.
old-location: display\d3d12ddiarg_create_video_decoder.htm
ms.assetid: 8178A279-96FE-40DC-A292-4551FA153F45
ms.date: 05/10/2018
ms.keywords: D3D12DDIARG_CREATE_VIDEO_DECODER_0021, D3D12DDIARG_CREATE_VIDEO_DECODER_0021 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_0021, display.d3d12ddiarg_create_video_decoder
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_CREATE_VIDEO_DECODER_0021"
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
req.max-support: Windows 10, version 1709
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDIARG_CREATE_VIDEO_DECODER_0021
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_CREATE_VIDEO_DECODER_0021
---

# D3D12DDIARG_CREATE_VIDEO_DECODER_0021 structure


## -description


Used to create a decoder object for a decode session.


## -struct-fields




### -field NodeMask

A node mask. For single GPU operation, set this value to zero (0). If there are multiple GPU nodes, set a bit to identify the physical adapter of the device to which the command queue applies. Each bit in the mask corresponds to a single node. Only one  bit may be set.


### -field Configuration

The decode profile and bitstream encryption.  For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.


### -field DecodeWidth

The decode width of the bitstream to be decoded.


### -field DecodeHeight

The decode height of the bitstream to be decoded.


### -field MaxDecodePictureBufferCount

The maximum number of decode picture buffers this stream can have.


### -field FrameRate

The frame rate of the input video stream.


### -field BitRate

The data compression rate, in bits per second, for the compressed video stream.


### -field Usage

A hint for the intended usage for the decoder stream. For more information, see the <a href="https://msdn.microsoft.com/663790EE-A9E3-4EBC-93C7-20DE0D759A26">D3D12DDI_VIDEO_USAGE</a> enumeration.





## -remarks



Drivers can use the <i>Bitrate</i> and <i>FrameRate</i> parameters to inform heuristics such as intermediate allocation sizes or performance optimizations.

Decoding a frame is allowed to fail if the <i>Bitrate</i> and <i>FrameRate</i> values are insufficient for the video stream.  If decode fails for this reason, the query <b>D3D12DDI_QUERY_TYPE_VIDEO_DECODE_STATISTICS</b> must return a status of <b>D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED</b>.

The <i>Bitrate</i> and <i>FrameRate</i> parameters may also be set to zero.  When these values are used, drivers must make worst case assumptions. They are not allowed to fail with <b>D3D12DDI_VIDEO_DECODE_STATUS_RATE_EXCEEDED</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/663790EE-A9E3-4EBC-93C7-20DE0D759A26">D3D12DDI_VIDEO_USAGE</a>
 

 

