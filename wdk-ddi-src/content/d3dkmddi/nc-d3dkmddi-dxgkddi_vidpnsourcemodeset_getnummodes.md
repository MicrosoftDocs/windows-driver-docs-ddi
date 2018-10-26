---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES
title: DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES
author: windows-driver-content
description: The pfnGetNumModes function returns the number of source modes in a specified VidPN source mode set.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfngetnummodes.htm
ms.assetid: abdc053c-45da-4af3-84c1-7eeb4a2856cb
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES, DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES callback, VidPnFunctions_e2cf0efc-e1a3-4515-b539-9c475877dd78.xml, d3dkmddi/pfnGetNumModes, display.dxgk_vidpnsourcemodeset_interface_pfngetnummodes, pfnGetNumModes, pfnGetNumModes callback function [Display Devices]
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnGetNumModes
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNSOURCEMODESET_GETNUMMODES callback function


## -description


The <b>pfnGetNumModes</b> function returns the number of source modes in a specified VidPN source mode set.


## -parameters




### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param pNumSourceModes [out]

[out] A pointer to a SIZE_T-typed variable that receives the number of source modes in the set.


## -returns



The <b>pfnGetNumModes</b> function returns one of the following values:

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_SOURCEMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnSourceModeSet</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/3af816e0-f1a4-4477-8735-6400aadfb57b">pfnAcquireFirstModeInfo</a>



<a href="https://msdn.microsoft.com/d9cb1ff1-c428-46e5-884a-5fc39e16300e">pfnAcquireNextModeInfo</a>
 

 

