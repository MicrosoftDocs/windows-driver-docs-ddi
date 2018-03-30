---
UID: NC:d3dkmthk.PFND3DKMT_SETVIDPNSOURCEOWNER1
title: PFND3DKMT_SETVIDPNSOURCEOWNER1
author: windows-driver-content
description: Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and lets output duplication options be specified. Supported starting with Windows 8.
old-location: display\d3dkmtsetvidpnsourceowner1.htm
old-project: display
ms.assetid: ccee5459-f156-41c3-b9a1-8bd7d16c8d19
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTSetVidPnSourceOwner1, D3DKMTSetVidPnSourceOwner1 callback function [Display Devices], PFND3DKMT_SETVIDPNSOURCEOWNER1, d3dkmthk/D3DKMTSetVidPnSourceOwner1, display.d3dkmtsetvidpnsourceowner1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3DKMTSetVidPnSourceOwner1
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PFND3DKMT_SETVIDPNSOURCEOWNER1 callback


## -description


Sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN, and  lets output duplication options be specified. Supported starting with Windows 8.


## -parameters




### -param *








#### - pSetVidPnSourceOwner1 [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406588">D3DKMT_SETVIDPNSOURCEOWNER1</a> structure that describes the parameters for setting or releasing the video present source.


## -returns



Returns one of the following values:

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
The video present source was successfully set or released.

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
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548317">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is invalid. 

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
 

This function might also return other NTSTATUS values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406588">D3DKMT_SETVIDPNSOURCEOWNER1</a>
 

 

