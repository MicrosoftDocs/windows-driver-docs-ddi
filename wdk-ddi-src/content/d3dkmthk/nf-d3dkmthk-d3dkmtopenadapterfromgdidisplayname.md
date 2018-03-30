---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromGdiDisplayName
title: D3DKMTOpenAdapterFromGdiDisplayName function
author: windows-driver-content
description: The D3DKMTOpenAdapterFromGdiDisplayName function maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.
old-location: display\d3dkmtopenadapterfromgdidisplayname.htm
old-project: display
ms.assetid: 56656fc2-785c-4021-9864-e4c152551973
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTOpenAdapterFromGdiDisplayName, D3DKMTOpenAdapterFromGdiDisplayName function [Display Devices], OpenGL_Functions_74419d9d-cd33-4fed-8103-3be487c3c7a1.xml, d3dkmthk/D3DKMTOpenAdapterFromGdiDisplayName, display.d3dkmtopenadapterfromgdidisplayname
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
-	API-MS-Win-DX-D3DKmt-l1-1-0.dll
-	API-MS-Win-DX-D3DKmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTOpenAdapterFromGdiDisplayName
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenAdapterFromGdiDisplayName function


## -description


The <b>D3DKMTOpenAdapterFromGdiDisplayName</b> function maps a GDI device name to a graphics adapter handle and, if the adapter contains multiple monitor outputs, to one of those outputs.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548113">D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME</a> structure that describes the parameters that are required to perform the mapping.


## -returns



<b>D3DKMTOpenAdapterFromGdiDisplayName</b>
       returns one of the following values:

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
The mapping was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.

</td>
</tr>
</table>
 

This function might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



A graphics adapter corresponds to a video card. A monitor output corresponds to a head on a video card. A system with a single video card contains only one adapter. However, if the video card supports multiple heads, it supports outputting to multiple monitors.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548113">D3DKMT_OPENADAPTERFROMGDIDISPLAYNAME</a>
 

 

