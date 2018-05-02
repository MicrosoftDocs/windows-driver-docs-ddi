---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020
author: windows-driver-content
description: The pfnGetDecodeProfileCount callback function retrieves the number of decode profiles supported by the driver.
old-location: display\pfnd3d12ddi_video_get_decode_profile_count.htm
old-project: display
ms.assetid: 81B31232-5207-46AF-952C-252E2512521F
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020, PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback, d3d12umddi/pfnGetDecodeProfileCount, display.pfnd3d12ddi_video_get_decode_profile_count, pfnGetDecodeProfileCount, pfnGetDecodeProfileCount callback function [Display Devices]
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
-	pfnGetDecodeProfileCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback function


## -description


 The <i>pfnGetDecodeProfileCount</i> callback function retrieves the number of decode profiles supported by the driver.


## -parameters




### -param Arg1

A handle to the display device (graphics context).

### -param NodeIndex

The physical adapter of the device to which this operation applies.


#### - hDrvDevice

The handle of a device.


## -returns



This function retrieves the count of decode profiles supported by the driver.




## -remarks



This function is called to retrieve the number of supported profiles.  The caller uses this value to allocate storage to retrieve the list of profiles.  The list is retrieved by using the <a href="https://msdn.microsoft.com/6875B754-115F-481D-8D46-2A383BA6B5E7">pfnGetCaps</a> callback function with the <a href="https://msdn.microsoft.com/C74697BF-A191-4371-9F23-7F655EBC53B3">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILES</b>.




## -see-also




<a href="https://msdn.microsoft.com/C74697BF-A191-4371-9F23-7F655EBC53B3">D3D12DDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/6875B754-115F-481D-8D46-2A383BA6B5E7">pfnGetCaps</a>
 

 

