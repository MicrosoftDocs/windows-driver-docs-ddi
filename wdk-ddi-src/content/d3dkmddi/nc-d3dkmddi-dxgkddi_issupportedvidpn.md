---
UID: NC:d3dkmddi.DXGKDDI_ISSUPPORTEDVIDPN
title: DXGKDDI_ISSUPPORTEDVIDPN
author: windows-driver-content
description: The DxgkDdiIsSupportedVidPn function determines whether a specified VidPN is supported on a display adapter.
old-location: display\dxgkddiissupportedvidpn.htm
old-project: display
ms.assetid: 96e96366-6306-4d20-8752-e942f2ed4069
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_ISSUPPORTEDVIDPN, DXGKDDI_ISSUPPORTEDVIDPN callback, DmFunctions_222f2c38-00c6-466f-b653-3c9529f93849.xml, DxgkDdiIsSupportedVidPn, DxgkDdiIsSupportedVidPn callback function [Display Devices], d3dkmddi/DxgkDdiIsSupportedVidPn, display.dxgkddiissupportedvidpn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
-	DxgkDdiIsSupportedVidPn
product: Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_ISSUPPORTEDVIDPN callback function


## -description


The <i>DxgkDdiIsSupportedVidPn</i> function determines whether a specified VidPN is supported on a display adapter.


## -parameters




### -param hAdapter [in]

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.


### -param pIsSupportedVidPn








#### - pIsSupportedVidPnArg [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557601">DXGKARG_ISSUPPORTEDVIDPN</a> structure. On input, the caller supplies the <b>hDesiredVidPn</b> member of the structure. On return, the <b>IsVidPnSupported</b> member receives a Boolean value that indicates whether the VidPN is supported (<b>TRUE</b>) or not supported (<b>FALSE</b>).


## -returns



<i>DxgkDdiIsSupportedVidPn</i> returns one of the following values

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
The topology of the VidPN is valid. The <b>IsVidPnSupported</b> structure member is set to either <b>TRUE</b> or <b>FALSE</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The topology of the VidPN implementation is invalid. The <b>IsVidPnSupported</b> structure member is set to <b>FALSE</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The function failed because it was unable to allocate memory.

</td>
</tr>
</table>
 




## -remarks



For more information about the analysis that this function must perform, see <a href="https://msdn.microsoft.com/ebf001fb-e445-4534-8e89-60e1b06b2d6e">Determining Whether a VidPN is Supported on a Display Adapter</a><u>.</u>

If pIsSupportedVidPnArg-&gt;hDesiredVidPn is zero, <i>DxgkDdiIsSupportedVidPn</i> must set pIsSupportedVidPnArg-&gt;IsVidPnSupported to <b>TRUE</b>, the idea being that the display adapter can always be configured to display nothing.

<i>DxgkDdiIsSupportedVidPn</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>
 

 

