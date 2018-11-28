---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
title: PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
author: windows-driver-content
description: The GetVideoProcessStreamStatePrivate function retrieves the private stream-state data for a video processor.
old-location: display\getvideoprocessstreamstateprivate.htm
tech.root: display
ms.assetid: 0503b382-8ed3-461e-906f-27953ac5f757
ms.date: 05/10/2018
ms.keywords: GetVideoProcessStreamStatePrivate, GetVideoProcessStreamStatePrivate callback function [Display Devices], PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE callback, UserModeDisplayDriver_Functions_1016a4a3-3988-40ef-9ef9-f62a20651aaa.xml, d3dumddi/GetVideoProcessStreamStatePrivate, display.getvideoprocessstreamstateprivate
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetVideoProcessStreamStatePrivate is supported beginning with the Windows 7 operating system.
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
-	GetVideoProcessStreamStatePrivate
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE callback function


## -description


The <i>GetVideoProcessStreamStatePrivate</i> function retrieves the private stream-state data for a video processor. 


## -parameters




### -param Arg1


### -param *








*hDevice* [in]

A handle to the display device (graphics context).


*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543089">D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE</a> structure that describes the private stream-state data to retrieve. 


## -returns



The <i>GetVideoProcessStreamStatePrivate</i> function returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The stream-state data is successfully retrieved.|
|E_OUTOFMEMORY|GetVideoProcessStreamStatePrivate could not allocate the required memory for it to complete.|

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543089">D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE</a>
 

 

