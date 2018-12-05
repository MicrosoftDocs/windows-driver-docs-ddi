---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD
title: PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD
author: windows-driver-content
description: The VideoProcessBltHD function processes video input streams and composes to an output surface.
old-location: display\videoprocessblthd.htm
tech.root: display
ms.assetid: 62451fc4-92cc-4553-80cc-0843cf734a62
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD, PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD callback, UserModeDisplayDriver_Functions_72b2babe-fc93-4960-93d3-6bc2022227c8.xml, VideoProcessBltHD, VideoProcessBltHD callback function [Display Devices], d3dumddi/VideoProcessBltHD, display.videoprocessblthd
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: VideoProcessBltHD is supported beginning with the Windows 7 operating system.
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
-	VideoProcessBltHD
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DXVAHD_VIDEOPROCESSBLTHD callback function


## -description


The <i>VideoProcessBltHD</i> function processes video input streams and composes to an output surface.


## -parameters




### -param Arg1


### -param *








*hDevice* [in]

A handle to the display device (graphics context).


*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543101">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a> structure that describes the DirectX VA video processing operation to perform. 


## -returns



<i>VideoProcessBltHD</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The DirectX VA video processing operation is successfully performed.|
|E_OUTOFMEMORY|VideoProcessBltHD could not allocate memory that was required for it to complete.|

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543101">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a>
 

 

