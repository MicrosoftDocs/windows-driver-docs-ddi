---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020
title: PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020
author: windows-driver-content
description: The pfnGetDecodeProfileCount callback function retrieves the number of decode profiles supported by the driver.
old-location: display\pfnd3d12ddi_video_get_decode_profile_count.htm
old-project: display
ms.assetid: 81B31232-5207-46AF-952C-252E2512521F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020, d3d12umddi/pfnGetDecodeProfileCount, display.pfnd3d12ddi_video_get_decode_profile_count, pfnGetDecodeProfileCount, pfnGetDecodeProfileCount callback function [Display Devices]
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
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnGetDecodeProfileCount
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback


## -description


 The <i>pfnGetDecodeProfileCount</i> callback function retrieves the number of decode profiles supported by the driver.


## -prototype


````
PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 pfnGetDecodeProfileCount;

UINT APIENTRY* pfnGetDecodeProfileCount(
   D3D12DDI_HDEVICE hDrvDevice,
   UINT             NodeIndex
)
{ ... }
````


## -parameters




### -param D3D12DDI_HDEVICE


### -param NodeIndex

The physical adapter of the device to which this operation applies.


#### - hDrvDevice

The handle of a device. 


## -returns



This function retrieves the count of decode profiles supported by the driver.




## -remarks



This function is called to retrieve the number of supported profiles.  The caller uses this value to allocate storage to retrieve the list of profiles.  The list is retrieved by using the <a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md">pfnGetCaps</a> callback function with the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddicaps_type.md">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_PROFILES</b>.




## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddicaps_type.md">D3D12DDICAPS_TYPE</a>



<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md">pfnGetCaps</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

