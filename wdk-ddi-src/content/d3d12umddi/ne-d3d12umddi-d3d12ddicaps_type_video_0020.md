---
UID: NE:d3d12umddi.D3D12DDICAPS_TYPE_VIDEO_0020
title: D3D12DDICAPS_TYPE_VIDEO_0020
author: windows-driver-content
description: Contains capability types for video.
old-location: display\d3d12ddicaps_type_video_0020.htm
old-project: display
ms.assetid: 3B95996D-EB7C-4DCF-B00C-BA5AFEFD4110
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDICAPS_TYPE_VIDEO_0020, D3D12DDICAPS_TYPE_VIDEO_0020
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
req.alt-api: D3D12DDICAPS_TYPE_VIDEO_0020
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D12DDICAPS_TYPE_VIDEO_0020
---

# D3D12DDICAPS_TYPE_VIDEO_0020 enumeration



## -description
Contains capability types for video.



## -syntax

````
typedef enum _D3D12DDICAPS_TYPE_VIDEO_0020 { 
  D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_SUPPORT                       = 0,
  D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES                      = 1,
  D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_FORMATS                       = 2,
  D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_CONVERSION_SUPPORT            = 3,
  D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES  = 4,
  D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_SUPPORT                      = 5,
  D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS            = 6,
  D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_REFERENCE_INFO               = 7
} D3D12DDICAPS_TYPE_VIDEO_0020;
````


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


## -remarks
