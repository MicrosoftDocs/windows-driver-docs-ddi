---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 (d3d12umddi.h)
description: The pfnGetDecodeFormatCount callback function retrieves the number of formats supported for a decode configuration.
old-location: display\pfnd3d12ddi_video_get_decode_format_count.htm
ms.assetid: 84503E38-E141-4DAC-B305-6C7E6157A3E9
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 callback function"]
ms.keywords: PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020, PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 callback, d3d12umddi/pfnGetDecodeFormatCount, display.pfnd3d12ddi_video_get_decode_format_count, pfnGetDecodeFormatCount, pfnGetDecodeFormatCount callback function [Display Devices]
f1_keywords:
 - "d3d12umddi/pfnGetDecodeFormatCount"
 - "pfnGetDecodeFormatCount"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnGetDecodeFormatCount
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020 callback function


## -description


The <i>pfnGetDecodeFormatCount</i> callback function retrieves the number of formats supported for a decode configuration.


## -parameters




### -param Arg1

A handle to the display device (graphics context).

### -param NodeIndex

The physical adapter of the device to which this operation applies.


### -param Arg3

*pConfiguration*

The decode configuration for the list of formats.  For more information, see the <a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.



## -returns



This function retrieves the number of formats supported for a decode configuration.




## -see-also




<a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">3D12DDI_VIDEO_DECODE_CONFIGURATION</a>
 

 