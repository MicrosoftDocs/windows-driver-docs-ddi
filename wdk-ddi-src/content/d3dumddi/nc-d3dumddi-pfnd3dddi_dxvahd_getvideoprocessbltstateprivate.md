---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE
title: PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE (d3dumddi.h)
description: The GetVideoProcessBltStatePrivate function retrieves the state data of a private bit-block transfer (bitblt) for a video processor.
old-location: display\getvideoprocessbltstateprivate.htm
tech.root: display
ms.assetid: bb4c04cf-0125-47bf-8fc8-88d807e7b6ad
ms.date: 05/10/2018
ms.keywords: GetVideoProcessBltStatePrivate, GetVideoProcessBltStatePrivate callback function [Display Devices], PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE, PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE callback, UserModeDisplayDriver_Functions_e39248ae-aa92-4c0a-aebc-a48f7d1e24a7.xml, d3dumddi/GetVideoProcessBltStatePrivate, display.getvideoprocessbltstateprivate
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetVideoProcessBltStatePrivate is supported beginning with the Windows 7 operating system.
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dumddi.h
api_name:
- GetVideoProcessBltStatePrivate
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE callback function


## -description


The <i>GetVideoProcessBltStatePrivate</i> function retrieves the state data of a private bit-block transfer (bitblt) for a video processor. 


## -parameters




### -param Arg1


### -param *


*hDevice* [in]

A handle to the display device (graphics context).


*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543086">D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE</a> structure that describes the private bitblt state data to retrieve. 


## -returns



The <i>GetVideoProcessBltStatePrivate</i> function returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The bitblt state data is successfully retrieved.|
|E_OUTOFMEMORY|GetVideoProcessBltStatePrivate could not allocate the required memory for it to complete.|


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543086">D3DDDIARG_DXVAHD_GETVIDEOPROCESSBLTSTATEPRIVATE</a>
 

 

