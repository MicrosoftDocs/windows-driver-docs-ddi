---
UID: NF:d3dkmthk.D3DKMTCheckVidPnExclusiveOwnership
title: D3DKMTCheckVidPnExclusiveOwnership function
author: windows-driver-content
description: The D3DKMTCheckVidPnExclusiveOwnership function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.
old-location: display\d3dkmtcheckvidpnexclusiveownership.htm
old-project: display
ms.assetid: 06333989-177c-4c58-b95a-60313c04fe35
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , 3, C, D, D3DKMTCheckVidPnExclusiveOwnership, D3DKMTCheckVidPnExclusiveOwnership callback function [Display Devices], E, K, M, O, OpenGL_Functions_edc90d51-f7e4-4bb5-be24-1a32b9fb4461.xml, P, PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, T, V, c, d, d3dkmthk/D3DKMTCheckVidPnExclusiveOwnership, display.d3dkmtcheckvidpnexclusiveownership, e, h, i, k, l, n, p, r, s, u, v, w, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMTCheckVidPnExclusiveOwnership
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCheckVidPnExclusiveOwnership function


## -description


The <b>D3DKMTCheckVidPnExclusiveOwnership</b> function determines the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN. 


## -syntax


````
NTSTATUS D3DKMTCheckVidPnExclusiveOwnership(
  _In_ const D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP *pData
);
````


## -parameters




### -param D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP

TBD




#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_checkvidpnexclusiveownership.md">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a> structure that describes the parameters to determine exclusive VidPN ownership. 


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
The video present source that is identified by the <b>VidPnSourceId</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_checkvidpnexclusiveownership.md">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a> is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source.

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_checkvidpnexclusiveownership.md">D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

