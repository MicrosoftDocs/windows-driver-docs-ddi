---
UID: NC:d3dumddi.PFND3DDDI_VIDEOPROCESSBEGINFRAME
title: PFND3DDDI_VIDEOPROCESSBEGINFRAME
description: The VideoProcessBeginFrame function notifies the user-mode display driver that processing of a video frame can begin on the specified Microsoft DirectX Video Accelerator (VA) video processing device.
old-location: display\videoprocessbeginframe.htm
tech.root: display
ms.assetid: 1b7b1774-3144-4929-83d8-c52a7de6936d
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_VIDEOPROCESSBEGINFRAME, PFND3DDDI_VIDEOPROCESSBEGINFRAME callback, UserModeDisplayDriver_Functions_c3ad6569-b0a0-4688-bd1a-f02a7176a2f2.xml, VideoProcessBeginFrame, VideoProcessBeginFrame callback function [Display Devices], d3dumddi/VideoProcessBeginFrame, display.videoprocessbeginframe
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dumddi.h
api_name:
-	VideoProcessBeginFrame
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_VIDEOPROCESSBEGINFRAME callback function


## -description


The <i>VideoProcessBeginFrame</i> function notifies the user-mode display driver that processing of a video frame can begin on the specified Microsoft DirectX Video Accelerator (VA) video processing device.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param hVideoProcess

[in] The handle to the DirectX VA video processing device that should start processing the video frame. The <a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a> function created this handle.


## -returns



<i>VideoProcessBeginFrame</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|Video frame processing successfully began.|
|E_OUTOFMEMORY|VideoProcessBeginFrame could not allocate the required memory for it to complete.|


## -remarks



The <i>VideoProcessBeginFrame</i> function notifies the user-mode display driver that its <a href="https://msdn.microsoft.com/719465dd-4547-491c-ab30-ae63bba1b72c">VideoProcessBlt</a> function can be called on the specified video processing device.




## -see-also




<a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/719465dd-4547-491c-ab30-ae63bba1b72c">VideoProcessBlt</a>
 

 

