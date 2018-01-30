---
UID: NF:d3dkmthk.D3DKMTSetDisplayPrivateDriverFormat
title: D3DKMTSetDisplayPrivateDriverFormat function
author: windows-driver-content
description: The D3DKMTSetDisplayPrivateDriverFormat function changes the private-format attribute of a video present source.
old-location: display\d3dkmtsetdisplayprivatedriverformat.htm
old-project: display
ms.assetid: 4b720076-161f-47b4-b410-f9554e502a53
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTSetDisplayPrivateDriverFormat function [Display Devices], d3dkmthk/D3DKMTSetDisplayPrivateDriverFormat, D3DKMTSetDisplayPrivateDriverFormat, display.d3dkmtsetdisplayprivatedriverformat, OpenGL_Functions_742fb584-0b9d-4650-a0a6-64f3e3f55dff.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTSetDisplayPrivateDriverFormat
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSetDisplayPrivateDriverFormat function


## -description


The <b>D3DKMTSetDisplayPrivateDriverFormat</b> function changes the private-format attribute of a video present source.


## -syntax


````
NTSTATUS APIENTRY D3DKMTSetDisplayPrivateDriverFormat(
  _In_ const D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT *pData
);
````


## -parameters




### -param D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT

TBD



#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setdisplayprivatedriverformat.md">D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that describes how to format a video present source.


## -returns


<b>D3DKMTSetDisplayPrivateDriverFormat</b> returns one of the following values:
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
The video present source was successfully changed.

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_NOT_EXCLUSIVE_MODE_OWNER</b></dt>
</dl>
</td>
<td width="60%">
Before the call to <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplayprivatedriverformat.md">D3DKMTSetDisplayPrivateDriverFormat</a>, the device did not acquire exclusive ownership of the view. Therefore, the device could not change the private-format attribute of the video present source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver does not support the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat.md">DxgkDdiSetDisplayPrivateDriverFormat</a> function. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The display miniport driver could not change the private-format attribute of the view for the video present source. 

</td>
</tr>
</table> 

This function might also return other NTSTATUS values.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setdisplayprivatedriverformat.md">D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat.md">DxgkDdiSetDisplayPrivateDriverFormat</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetDisplayPrivateDriverFormat function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

