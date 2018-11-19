---
UID: NC:d3dumddi.PFND3DDDI_VIDEOPROCESSENDFRAME
title: PFND3DDDI_VIDEOPROCESSENDFRAME
author: windows-driver-content
description: The VideoProcessEndFrame function notifies the user-mode display driver that all of the data that is required to process the current frame was submitted.
old-location: display\videoprocessendframe.htm
tech.root: display
ms.assetid: a5be6834-bb27-4da0-8802-25a9ca58c101
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_VIDEOPROCESSENDFRAME, PFND3DDDI_VIDEOPROCESSENDFRAME callback, UserModeDisplayDriver_Functions_b7ef391b-90b5-49a6-880e-d0c4f287d0ad.xml, VideoProcessEndFrame, VideoProcessEndFrame callback function [Display Devices], d3dumddi/VideoProcessEndFrame, display.videoprocessendframe
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
-	VideoProcessEndFrame
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_VIDEOPROCESSENDFRAME callback function


## -description


The <i>VideoProcessEndFrame</i> function notifies the user-mode display driver that all of the data that is required to process the current frame was submitted.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544109">D3DDDIARG_VIDEOPROCESSENDFRAME</a> structure that describes the DirectX VA video processor that should stop processing a frame.


## -returns



<i>VideoProcessEndFrame</i> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | Processing of the current frame is successfully completed. | 
| **E_OUTOFMEMORY** | VideoProcessEndFrame cannot allocate memory required for it to complete. | 


## -remarks



The <i>VideoProcessEndFrame</i> function notifies the user-mode display driver that its <a href="https://msdn.microsoft.com/719465dd-4547-491c-ab30-ae63bba1b72c">VideoProcessBlt</a> function can no longer be called on the specified video processing device.




## -see-also




<a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544109">D3DDDIARG_VIDEOPROCESSENDFRAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/719465dd-4547-491c-ab30-ae63bba1b72c">VideoProcessBlt</a>
 

 

