---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_RELEASESOURCEMODESET
title: DXGKDDI_VIDPN_RELEASESOURCEMODESET
author: windows-driver-content
description: The pfnReleaseSourceModeSet function releases a handle to a source mode set object.
old-location: display\dxgk_vidpn_interface_pfnreleasesourcemodeset.htm
old-project: display
ms.assetid: f1ee8761-f36e-4a39-a78e-95975442f7d3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_VIDPN_RELEASESOURCEMODESET, DXGKDDI_VIDPN_RELEASESOURCEMODESET callback, VidPnFunctions_601f59ab-13a9-4c65-8c94-6a7d962c01f9.xml, d3dkmddi/pfnReleaseSourceModeSet, display.dxgk_vidpn_interface_pfnreleasesourcemodeset, pfnReleaseSourceModeSet, pfnReleaseSourceModeSet callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	pfnReleaseSourceModeSet
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_VIDPN_RELEASESOURCEMODESET callback function


## -description


The <b>pfnReleaseSourceModeSet</b> function releases a handle to a source mode set object.


## -parameters




### -param hVidPn [in]

[in] A handle to the VidPN object that contains the source mode set object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://msdn.microsoft.com/96e96366-6306-4d20-8752-e942f2ed4069">DxgkDdiIsSupportedVidPn</a>, or <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a>.


### -param hVidPnSourceModeSet [in]

[in] The handle to be released.


## -returns



The <b>pfnReleaseSourceModeSet</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPn</i> was invalid.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_RESOURCES_NOT_RELATED</b></dt>
</dl>
</td>
<td width="60%">
The VidPN identified by <i>hVidPn</i> does not contain the source mode set identified by <i>hVidPnSourceModeSet</i>.

</td>
</tr>
</table>
 




## -remarks



When you have finished using a handle that you obtained by calling <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a>, you must release the handle by calling <b>pfnReleaseSourceModeSet</b>.

If you obtain a handle by calling <a href="https://msdn.microsoft.com/d46ffa49-6e75-4cd4-9d14-aa2c9fa671be">pfnCreateNewSourceModeSet</a> and then pass that handle to <a href="https://msdn.microsoft.com/e1a2ca9e-9035-4656-bcb8-4ad956a8501d">pfnAssignSourceModeSet</a>, you do not need to release the handle.

If you obtain a handle by calling <b>pfnCreateNewSourceModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseSourceModeSet</b>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNSOURCEMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a>



<a href="https://msdn.microsoft.com/d46ffa49-6e75-4cd4-9d14-aa2c9fa671be">pfnCreateNewSourceModeSet</a>
 

 

