---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
title: PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR
author: windows-driver-content
description: The CreateVideoProcessor function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video.
old-location: display\createvideoprocessor.htm
tech.root: display
ms.assetid: 68a7c394-4b0f-4446-a54b-5aee6cf8a913
ms.date: 5/10/2018
ms.keywords: CreateVideoProcessor, CreateVideoProcessor callback function [Display Devices], PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR, PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback, UserModeDisplayDriver_Functions_ce6a0d51-9da3-43d9-ac23-c2e250ca4cfa.xml, d3dumddi/CreateVideoProcessor, display.createvideoprocessor
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateVideoProcessor is supported beginning with the Windows 7 operating system.
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
-	CreateVideoProcessor
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DXVAHD_CREATEVIDEOPROCESSOR callback function


## -description


The <b>CreateVideoProcessor</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) video processor that is used to process high-definition video. 


## -parameters




### -param Arg1


### -param *








*hDevice* [in]

A handle to the display device (graphics context).


*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543077">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a> structure. On input, contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.


## -returns



<b>CreateVideoProcessor</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The video processor is successfully created. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/68a7c394-4b0f-4446-a54b-5aee6cf8a913">CreateVideoProcessor</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543077">D3DDDIARG_DXVAHD_CREATEVIDEOPROCESSOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451638">DestroyVideoProcessor</a>
 

 

