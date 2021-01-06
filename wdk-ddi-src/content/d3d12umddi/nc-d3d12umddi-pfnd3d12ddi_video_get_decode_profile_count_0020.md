---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 (d3d12umddi.h)
description: The pfnGetDecodeProfileCount callback function retrieves the number of decode profiles supported by the driver.
old-location: display\pfnd3d12ddi_video_get_decode_profile_count.htm
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback function"]
ms.keywords: PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020, PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback, d3d12umddi/pfnGetDecodeProfileCount, display.pfnd3d12ddi_video_get_decode_profile_count, pfnGetDecodeProfileCount, pfnGetDecodeProfileCount callback function [Display Devices]
f1_keywords:
 - "d3d12umddi/pfnGetDecodeProfileCount"
 - "pfnGetDecodeProfileCount"
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
- pfnGetDecodeProfileCount
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback function


## -description


The <i>pfnGetDecodeProfileCount</i> callback function retrieves the number of decode profiles supported by the driver.


## -parameters




### -param Arg1

*hDrvDevice*

A handle to the display device (graphics context).

### -param NodeIndex

The physical adapter of the device to which this operation applies.


## -returns



This function retrieves the count of decode profiles supported by the driver.




## -remarks



This function is called to retrieve the number of supported profiles.  The caller uses this value to allocate storage to retrieve the list of profiles.  The list is retrieved by using the <a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_video_getcaps">pfnGetCaps</a> callback function with the <a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddicaps_type">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILES</b>.




## -see-also




<a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddicaps_type">D3D12DDICAPS_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_video_getcaps">pfnGetCaps</a>
 

 
