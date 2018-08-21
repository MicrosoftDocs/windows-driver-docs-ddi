---
UID: NC:d3dkmddi.DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO
title: DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO
author: windows-driver-content
description: The pfnReleaseModeInfo function releases a D3DKMDT_VIDPN_SOURCE_MODE structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_vidpnsourcemodeset_interface_pfnreleasemodeinfo.htm
ms.assetid: 614283cc-90bf-44f2-bab2-1aeec5e7de01
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO, DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO callback, VidPnFunctions_4516c897-bcf8-4a32-9517-45c86690d746.xml, d3dkmddi/pfnReleaseModeInfo, display.dxgk_vidpnsourcemodeset_interface_pfnreleasemodeinfo, pfnReleaseModeInfo, pfnReleaseModeInfo callback function [Display Devices]
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
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNSOURCEMODESET_RELEASEMODEINFO callback function


## -description


The <b>pfnReleaseModeInfo</b> function releases a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a> structure that the VidPN manager previously provided to the display miniport driver.


## -parameters




### -param hVidPnSourceModeSet [in]

[in] A handle to a VidPN source mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/cf19f468-86c1-4cc9-8945-e23f73a85c91">pfnAcquireSourceModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnSourceModeInfo [in]

[in] A pointer to the D3DKMDT_VIDPN_SOURCE_MODE structure that is to be released.


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
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE_MODE</b></dt>
</dl>
</td>
<td width="60%">
The pointer supplied in <i>pVidPnSourceModeInfo </i>was invalid.

</td>
</tr>
</table>
 




## -remarks



When you have finished using a D3DKMDT_VIDPN_SOURCE_MODE structure that you obtained by calling any of the following functions, you must release the structure by calling <b>pfnReleaseModeInfo</b>.

<ul>
<li>

<a href="https://msdn.microsoft.com/3af816e0-f1a4-4477-8735-6400aadfb57b">pfnAcquireFirstModeInfo</a>


</li>
<li>

<a href="https://msdn.microsoft.com/d9cb1ff1-c428-46e5-884a-5fc39e16300e">pfnAcquireNextModeInfo</a>


</li>
<li>

<a href="https://msdn.microsoft.com/e757852b-ee68-4b07-83c8-9dfd089d1ab7">pfnAcquirePinnedModeInfo</a>


</li>
</ul>
If you obtain a D3DKMDT_VIDPN_SOURCE_MODE structure by calling <a href="https://msdn.microsoft.com/b18aab68-7457-45eb-8641-0b6180cfa70e">pfnCreateNewModeInfo</a> and then pass that structure to <a href="https://msdn.microsoft.com/754078c2-f79b-4237-a14c-96903856f3a5">pfnAddMode</a>, you do not need to release the structure.

If you obtain a handle by calling <b>pfnCreateNewModeInfo</b> and then you decide not to add the new mode to a source mode set, you must release the newly created structure by calling <b>pfnReleaseModeInfo</b>.

The D3DKMDT_HVIDPNSOURCEMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546724">D3DKMDT_VIDPN_SOURCE_MODE</a>



<a href="https://msdn.microsoft.com/3af816e0-f1a4-4477-8735-6400aadfb57b">pfnAcquireFirstModeInfo</a>



<a href="https://msdn.microsoft.com/d9cb1ff1-c428-46e5-884a-5fc39e16300e">pfnAcquireNextModeInfo</a>



<a href="https://msdn.microsoft.com/e757852b-ee68-4b07-83c8-9dfd089d1ab7">pfnAcquirePinnedModeInfo</a>
 

 

