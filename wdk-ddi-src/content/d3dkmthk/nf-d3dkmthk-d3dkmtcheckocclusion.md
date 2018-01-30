---
UID: NF:d3dkmthk.D3DKMTCheckOcclusion
title: D3DKMTCheckOcclusion function
author: windows-driver-content
description: The D3DKMTCheckOcclusion function verifies whether the client area of a window is occluded.
old-location: display\d3dkmtcheckocclusion.htm
old-project: display
ms.assetid: ce889a72-5f42-4bcf-aa15-6ec9b0423781
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dkmtcheckocclusion, D3DKMTCheckOcclusion, PFND3DKMT_CHECKOCCLUSION, D3DKMTCheckOcclusion function [Display Devices], OpenGL_Functions_a73b8485-971d-47a7-bc42-77bd709c5a74.xml, d3dkmthk/D3DKMTCheckOcclusion
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
-	D3DKMTCheckOcclusion
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCheckOcclusion function


## -description


The <b>D3DKMTCheckOcclusion</b> function verifies whether the client area of a window is occluded.


## -syntax


````
NTSTATUS APIENTRY D3DKMTCheckOcclusion(
  _In_ const D3DKMT_CHECKOCCLUSION *pData
);
````


## -parameters




### -param D3DKMT_CHECKOCCLUSION

TBD



#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_checkocclusion.md">D3DKMT_CHECKOCCLUSION</a> structure that describes parameters for checking occlusion.


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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_checkocclusion.md">D3DKMT_CHECKOCCLUSION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCheckOcclusion function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

