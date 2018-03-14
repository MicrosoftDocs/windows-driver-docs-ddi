---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
title: D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
author: windows-driver-content
description: Specifies information used to retrieve a list of supported formats for a decode configuration.
old-location: display\d3d12ddi_video_decode_formats_data.htm
old-project: display
ms.assetid: 0FF0F184-60FF-4467-ABF5-E05893083B25
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020 structure


## -description


Specifies information used to retrieve a list of supported formats for a decode configuration.


## -syntax


````
typedef struct D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020 {
  UINT                                     NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020 Configuration;
  UINT                                     FormatCount;
  DXGI_FORMAT                              *pOutputFormats;
} D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020;
````


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field Configuration

Specifies the decode configuration for the list of formats.


### -field FormatCount

The number of formats to retrieve.  The runtime ensures this value matches the value returned from PFND3D12DDI_VIDEO_GETCAPS with D3D12DDI_CAPSTYPE_VIDEO set to D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILE_FORMAT_COUNT.


### -field pOutputFormats

A pointer to the returned supported formats.  The calling application allocates storage for the format list.


## -see-also

<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_get_decode_format_count_0020.md">pfnGetDecodeFormatCount</a>



 

 


