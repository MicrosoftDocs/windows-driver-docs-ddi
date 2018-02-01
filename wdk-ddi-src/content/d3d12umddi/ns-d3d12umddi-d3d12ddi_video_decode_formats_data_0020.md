---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
title: D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020
author: windows-driver-content
description: Specifies information used to retrieve a list of supported formats for a decode configuration.
old-location: display\d3d12ddi_video_decode_formats_data.htm
old-project: display
ms.assetid: 0FF0F184-60FF-4467-ABF5-E05893083B25
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d12ddi_video_decode_formats_data, D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020, D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020 structure [Display Devices]
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_DECODE_FORMATS_DATA_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

