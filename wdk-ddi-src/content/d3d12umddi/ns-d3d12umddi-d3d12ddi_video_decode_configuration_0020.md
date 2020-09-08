---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
title: D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 (d3d12umddi.h)
description: Includes information about the video decode configuration.
old-location: display\d3d12ddi_video_decode_configuration.htm
ms.assetid: D689A7F3-87ED-4247-A28D-333C05C958F8
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020, D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020, display.d3d12ddi_video_decode_configuration
req.header: d3d12umddi.h
req.include-header: 
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
req.typenames: D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
f1_keywords:
 - D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
 - d3d12umddi/D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020
---

# D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 structure


## -description

Includes information about the video decode configuration. Contains common parameters for checking capabilities and creating the decoder, decode stream, and the crypto session objects.

## -struct-fields

### -field DecodeProfile

The profile for the decoder we want, e.g., HEVC_10BIT, HEVC_8BIT, H264_MAIN.

### -field BitstreamEncryption

The GUID identifying the encryption, e.g., D3D12DDI_DECODER_ENCRYPTION_HW_CENC.

### -field InterlaceType

The interlace type used by the coded frames. See [D3D12DDI_VIDEO_CODED_INTERLACE_TYPE](ne-d3d12umddi-d3d12ddi_video_coded_interlace_type_0020.md).

## -remarks

The decoder object represents a decode session and may contain tracking structures for the overall stream decode. Any significant allocations are expected to live within the decoder heap object.

