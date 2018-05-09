---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO
title: DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO
author: windows-driver-content
description: The pfnReleaseModeInfo function releases a D3DKMDT_VIDPN_TARGET_MODE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnreleasemodeinfo.htm
old-project: display
ms.assetid: 0b1d0331-f0fa-40fc-a1d6-15fe3568f3cc
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO, DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO callback, VidPnFunctions_faa4fee3-0bf7-43af-a000-e5b7e891c9e9.xml, d3dkmddi/pfnReleaseModeInfo, display.dxgk_vidpntargetmodeset_interface_pfnreleasemodeinfo, pfnReleaseModeInfo, pfnReleaseModeInfo callback function [Display Devices]
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
-	pfnReleaseModeInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_VIDPNTARGETMODESET_RELEASEMODEINFO callback function


## -description


The <b>pfnReleaseModeInfo</b> function releases a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure that the VidPN manager previously provided to the display miniport driver.


## -parameters




### -param hVidPnTargetModeSet [in]

[in] A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnTargetModeInfo [in]

[in] A pointer to the D3DKMDT_VIDPN_TARGET_MODE structure that is to be released.


## -returns



The <b>pfnReleaseModeInfo</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET_MODE</b></dt>
</dl>
</td>
<td width="60%">
The pointer supplied in <i>pVidPnTargetModeInfo</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



When you have finished using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a> structure that you obtained by calling any of the following functions, you must release the structure by calling <b>pfnReleaseModeInfo</b>.

<ul>
<li>

<a href="https://msdn.microsoft.com/64a1a8f4-afbc-4337-b809-9346c1171e0b">pfnAcquireFirstModeInfo</a>


</li>
<li>

<a href="https://msdn.microsoft.com/894d0d15-d12a-4138-9a92-8f930c12dd52">pfnAcquireNextModeInfo</a>


</li>
<li>

<a href="https://msdn.microsoft.com/0a321ee2-f246-498d-b658-a01e275644be">pfnAcquirePinnedModeInfo</a>


</li>
</ul>
If you obtain a D3DKMDT_VIDPN_TARGET_MODE structure by calling <a href="https://msdn.microsoft.com/ebb37681-fa03-49f5-968b-87c9ff4ebae9">pfnCreateNewModeInfo</a> and then pass that structure to <a href="https://msdn.microsoft.com/96c14056-aa93-4164-8adf-31fa1b3d33d3">pfnAddMode</a>, you do not need to release the structure.

If you obtain a handle by calling <b>pfnCreateNewModeInfo</b> and then you decide not to add the new mode to a target mode set, you must release the newly created structure by calling <b>pfnReleaseModeInfo</b>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546729">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="https://msdn.microsoft.com/64a1a8f4-afbc-4337-b809-9346c1171e0b">pfnAcquireFirstModeInfo</a>



<a href="https://msdn.microsoft.com/894d0d15-d12a-4138-9a92-8f930c12dd52">pfnAcquireNextModeInfo</a>



<a href="https://msdn.microsoft.com/0a321ee2-f246-498d-b658-a01e275644be">pfnAcquirePinnedModeInfo</a>
 

 

