---
UID: NC:d3dkmthk.PFND3DKMT_CHECKOCCLUSION
title: PFND3DKMT_CHECKOCCLUSION
author: windows-driver-content
description: The D3DKMTCheckOcclusion function verifies whether the client area of a window is occluded.
old-location: display\d3dkmtcheckocclusion.htm
old-project: display
ms.assetid: ce889a72-5f42-4bcf-aa15-6ec9b0423781
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTCheckOcclusion, D3DKMTCheckOcclusion callback function [Display Devices], OpenGL_Functions_a73b8485-971d-47a7-bc42-77bd709c5a74.xml, PFND3DKMT_CHECKOCCLUSION, d3dkmthk/D3DKMTCheckOcclusion, display.d3dkmtcheckocclusion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
-	d3dkmthk.h
api_name:
-	D3DKMTCheckOcclusion
product:
- Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PFND3DKMT_CHECKOCCLUSION callback


## -description


The <b>D3DKMTCheckOcclusion</b> function verifies whether the client area of a window is occluded.


## -parameters




### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547306">D3DKMT_CHECKOCCLUSION</a> structure that describes parameters for checking occlusion.


## -returns



<b>D3DKMTCheckOcclusion</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The client area of the window is not occluded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_PRESENT_OCCLUDED</b></dt>
</dl>
</td>
<td width="60%">
The client area of the window is occluded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -remarks



The handle to the window that is checked for occlusion must be valid. A window is not occluded if a part of its client area lies on a unowned video present network (VidPn) source, if its client area is an empty rectangular area (RECT), or if desktop composition is running.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547306">D3DKMT_CHECKOCCLUSION</a>
 

 

