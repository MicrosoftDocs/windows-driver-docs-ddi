---
UID: NC:d3dkmthk.PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
title: PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
author: windows-driver-content
description: The D3DKMTCheckVidPnExclusiveOwnership function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.
old-location: display\d3dkmtcheckvidpnexclusiveownership.htm
old-project: display
ms.assetid: 06333989-177c-4c58-b95a-60313c04fe35
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTCheckVidPnExclusiveOwnership, D3DKMTCheckVidPnExclusiveOwnership callback function [Display Devices], OpenGL_Functions_edc90d51-f7e4-4bb5-be24-1a32b9fb4461.xml, PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, d3dkmthk/D3DKMTCheckVidPnExclusiveOwnership, display.d3dkmtcheckvidpnexclusiveownership
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCheckVidPnExclusiveOwnership is supported beginning with the Windows 7 operating system.
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
-	D3DKMTCheckVidPnExclusiveOwnership
product:
- Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP callback


## -description


The <b>D3DKMTCheckVidPnExclusiveOwnership</b> function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN. 


## -parameters




### -param *








#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547784">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a> structure that describes the parameters to determine exclusive VidPN ownership. 


## -returns



<b>D3DKMTCheckVidPnExclusiveOwnership</b> returns one of the following values:

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
Exclusive ownership of the VidPN was successfully determined. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_VIDPN_SOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is identified by the <b>VidPnSourceId</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff547784">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a> is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is identified by the <b>VidPnSourceId</b> member of D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is invalid. 

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




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547784">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a>
 

 

