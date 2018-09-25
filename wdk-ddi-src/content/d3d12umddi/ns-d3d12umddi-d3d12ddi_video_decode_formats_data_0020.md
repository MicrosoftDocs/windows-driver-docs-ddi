---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
title: D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
author: windows-driver-content
description: Specifies information used to retrieve a list of supported formats for a decode configuration.
old-location: display\d3d12ddi_video_decode_formats_data.htm
ms.assetid: 0FF0F184-60FF-4467-ABF5-E05893083B25
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020, D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020, display.d3d12ddi_video_decode_formats_data
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020 structure


## -description


Specifies information used to retrieve a list of supported formats for a decode configuration.


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field Configuration

Specifies the decode configuration for the list of formats.


### -field FormatCount

The number of formats to retrieve. The runtime ensures this value matches the value returned from [PFND3D12DDI_VIDEO_GETCAPS](nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md) with D3D12DDI_CAPSTYPE_VIDEO set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_FORMAT_COUNT.


### -field pOutputFormats

A pointer to the returned supported formats. The calling application allocates storage for the format list.

## -remarks

These methods allow the list of supported decode formats supported by hardware. First, use PFND3D12DDDI_VIDEO_GETCAPS is called with D3D12DDICAPS_TYPE_VIDEO set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_FORMAT_COUNT to retrieve the number of supported formats. The caller uses this to allocate storage to retrieve the list of formats. The list is then retrieved through PFND3D12DDI_VIDEO_GETCAPS with the D3D12DDICAPS_TYPE set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_FORMATS.

## -see-also




 

 

