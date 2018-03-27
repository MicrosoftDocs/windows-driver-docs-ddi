---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020
author: windows-driver-content
description: The pfnGetDecodeFormatCount callback function retrieves the number of formats supported for a decode configuration.
old-location: display\pfnd3d12ddi_video_get_decode_format_count.htm
old-project: display
ms.assetid: 84503E38-E141-4DAC-B305-6C7E6157A3E9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020, d3d12umddi/pfnGetDecodeFormatCount, display.pfnd3d12ddi_video_get_decode_format_count, pfnGetDecodeFormatCount, pfnGetDecodeFormatCount callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.max-support: Windows 10, version 1709
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
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnGetDecodeFormatCount
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 callback


## -description


The <i>pfnGetDecodeFormatCount</i> callback function retrieves the number of formats supported for a decode configuration.


## -prototype


````
PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 pfnGetDecodeFormatCount;

UINT APIENTRY* pfnGetDecodeFormatCount(
         D3D12DDI_HDEVICE                    hDrvDevice,
         UINT                                NodeIndex,
   const D3D12DDI_VIDEO_DECODE_CONFIGURATION *pConfiguration
)
{ ... }
````


## -parameters




### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param NodeIndex

The physical adapter of the device to which this operation applies.


### -param *





#### - pConfiguration

The decode configuration for the list of formats.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.


## -returns



This function retrieves the number of formats supported for a decode configuration.




## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



 

 


