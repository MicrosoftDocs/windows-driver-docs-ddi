---
UID: NE:d3d12umddi.D3D12DDICAPS_TYPE_VIDEO_0020
title: D3D12DDICAPS_TYPE_VIDEO_0020
author: windows-driver-content
description: Contains capability types for video.
old-location: display\d3d12ddicaps_type_video_0020.htm
old-project: display
ms.assetid: 3B95996D-EB7C-4DCF-B00C-BA5AFEFD4110
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDICAPS_TYPE_VIDEO_0020, D3D12DDICAPS_TYPE_VIDEO_0020 enumeration [Display Devices], D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES, D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO, D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO, d3d12umddi/D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT, display.d3d12ddicaps_type_video_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDICAPS_TYPE_VIDEO_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDICAPS_TYPE_VIDEO_0020
---

# D3D12DDICAPS_TYPE_VIDEO_0020 enumeration


## -description


Contains capability types for video.


## -enum-fields




### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT

Check if a decode profile, bitstream encryption, resolution, and format are supported


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES

Retrieve the list of decode profiles supported by the adapter.  


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS

 Retrieves the supported decode formats. 


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT

Check whether a colorspace conversion, format conversion, and scale are supported.  


### -field D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES

Retrieve the list of bitstream encryption schemes supported by the adapter. 


### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT

Retrieves the video processor capabilities.  


### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS

The maximum number of streams that can be enabled at the same time.


### -field D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO

Retrieves the number of past and future frames required for a given deinterlace mode, filters, frame rate conversion, and features.  


### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODER_HEAP_SIZE


### -field D3D12DDICAPS_TYPE_VIDEO_0032_PROCESSOR_SIZE


### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_PROFILE_COUNT


### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_FORMAT_COUNT


### -field D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT


### -field D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_SUPPORT


### -field D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_COUNT


### -field D3D12DDICAPS_TYPE_VIDEO_0032_CONTENT_PROTECTION_SYSTEM_SUPPORT


### -field D3D12DDICAPS_TYPE_VIDEO_0032_CRYPTO_SESSION_TRANSFORM_SUPPORT



