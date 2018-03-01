---
UID: NF:d3dkmthk.D3DKMTGetDisplayModeList
title: D3DKMTGetDisplayModeList function
author: windows-driver-content
description: The D3DKMTGetDisplayModeList function retrieves a list of available display modes, including modes with extended format.
old-location: display\d3dkmtgetdisplaymodelist.htm
old-project: display
ms.assetid: f813171d-1c7d-4f75-850f-225ea166ff5c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTGetDisplayModeList, D3DKMTGetDisplayModeList function [Display Devices], OpenGL_Functions_a132bdb6-955b-4af3-a928-f834f5fdf440.xml, d3dkmthk/D3DKMTGetDisplayModeList, display.d3dkmtgetdisplaymodelist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTGetDisplayModeList
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTGetDisplayModeList function


## -description


The <b>D3DKMTGetDisplayModeList</b> function retrieves a list of available display modes, including modes with extended format.


## -syntax


````
NTSTATUS D3DKMTGetDisplayModeList(
  _Inout_ D3DKMT_GETDISPLAYMODELIST *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md">D3DKMT_GETDISPLAYMODELIST</a> structure that describes a list of available display modes.


## -returns



<b>D3DKMTGetDisplayModeList</b> returns one of the following values:

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
The list of available display modes was successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the OpenGL ICD supplied in the <b>pModeList</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md">D3DKMT_GETDISPLAYMODELIST</a> that the <i>pData</i> parameter points to is not large enough to contain the requested display mode list. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_NO_AVAILABLE_VIDPN_TARGET</b></dt>
</dl>
</td>
<td width="60%">
No video present target is available for use with the video present source that is identified by the <b>VidPnSourceId</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md">D3DKMT_GETDISPLAYMODELIST</a> that the <i>pData</i> parameter points to. Therefore, no display modes are available for this source. 

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md">D3DKMT_GETDISPLAYMODELIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTGetDisplayModeList function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

