---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_RELEASETARGETMODESET
title: DXGKDDI_VIDPN_RELEASETARGETMODESET
author: windows-driver-content
description: The pfnReleaseTargetModeSet function releases a handle to a target mode set object.
old-location: display\dxgk_vidpn_interface_pfnreleasetargetmodeset.htm
ms.assetid: bd369651-57d4-406f-ba51-9632362de15d
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPN_RELEASETARGETMODESET, DXGKDDI_VIDPN_RELEASETARGETMODESET callback, VidPnFunctions_c1609a38-53ff-49e0-a11a-26ceb5d64cdb.xml, d3dkmddi/pfnReleaseTargetModeSet, display.dxgk_vidpn_interface_pfnreleasetargetmodeset, pfnReleaseTargetModeSet, pfnReleaseTargetModeSet callback function [Display Devices]
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
-	pfnReleaseTargetModeSet
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPN_RELEASETARGETMODESET callback function


## -description


The <b>pfnReleaseTargetModeSet</b> function releases a handle to a target mode set object.


## -parameters




### -param hVidPn [in]

[in] A handle to a VidPN object that contains the target mode set object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://msdn.microsoft.com/96e96366-6306-4d20-8752-e942f2ed4069">DxgkDdiIsSupportedVidPn</a>, or <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a>.


### -param hVidPnTargetModeSet [in]

[in] The handle to be released.


## -returns



The <b>pfnReleaseTargetModeSet</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTargetModeSet</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_RESOURCES_NOT_RELATED</b></dt>
</dl>
</td>
<td width="60%">
The VidPN identified by <i>hVidPn</i> does not contain the target mode set identified by <i>hVidPnTargetModeSet</i>.

</td>
</tr>
</table>
 




## -remarks



When you have finished using a handle that you obtained by calling <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a>, you must release the handle by calling <b>pfnReleaseTargetModeSet</b>.

If you obtain a handle by calling <a href="https://msdn.microsoft.com/c52935b4-306f-4200-80d9-0cfab6998450">pfnCreateNewTargetModeSet</a> and then pass that handle to <a href="https://msdn.microsoft.com/846c6dd5-d4f8-4835-83a2-994725deaf36">pfnAssignTargetModeSet</a>, you do not need to release the handle.

If you obtain a handle by calling <b>pfnCreateNewTargetModeSet</b> and then you decide not to assign the new source mode set to a source, you must release the newly obtained handle by calling <b>pfnReleaseTargetModeSet</b>.

The D3DKMDT_HVIDPN and D3DKMDT_HVIDPNTARGETMODESET data types are defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a>



<a href="https://msdn.microsoft.com/c52935b4-306f-4200-80d9-0cfab6998450">pfnCreateNewTargetModeSet</a>
 

 

