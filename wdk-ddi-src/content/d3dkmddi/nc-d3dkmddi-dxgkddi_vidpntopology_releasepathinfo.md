---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO (d3dkmddi.h)
description: The pfnReleasePathInfo function releases a D3DKMDT_VIDPN_PRESENT_PATH structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_vidpntopology_interface_pfnreleasepathinfo.htm
ms.assetid: fdd34377-6b11-4005-93f1-ab42be7633c2
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO, DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO callback, VidPnFunctions_2bbba27c-cbbe-40ea-9ba6-0da2d7d237d5.xml, d3dkmddi/pfnReleasePathInfo, display.dxgk_vidpntopology_interface_pfnreleasepathinfo, pfnReleasePathInfo, pfnReleasePathInfo callback function [Display Devices]
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
-	pfnReleasePathInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO callback function


## -description


The <b>pfnReleasePathInfo</b> function releases a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that the VidPN manager previously provided to the display miniport driver.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnPresentPathInfo [in]

[in] A pointer to the D3DKMDT_VIDPN_PRESENT_PATH structure that is to be released.


## -returns



The <b>pfnReleasePathInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|
|STATUS_GRAPHICS_INVALID_VIDPN_PRESENT_PATH|The pointer supplied in pVidPnPresentPathInfo was invalid.|



## -remarks



When you have finished using a D3DKMDT_VIDPN_PRESENT_PATH structure that you obtained by calling any of the following functions, you must release the structure by calling <b>pfnReleasePathInfo</b>.

<ul>
<li>

<a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a>


</li>
<li>

<a href="https://msdn.microsoft.com/9f09ac0e-057c-48fb-a246-35e8ed7ddfc2">pfnAcquireNextPathInfo</a>


</li>
<li>

<a href="https://msdn.microsoft.com/27a03106-a5b5-489c-968a-81b3ea9940cb">pfnAcqirePathInfo</a>


</li>
</ul>
If you obtain a D3DKMDT_VIDPN_PRESENT_PATH structure by calling <b><u>pfnCreateNewPathInfo</u></b> and then pass that structure to <b><u>pfnAddPath</u></b>, you do not need to release the structure.

If you obtain a handle by calling <b>pfnCreateNewPathInfo</b> and then you decide not to add the new path to a topology, you must release the newly created structire by calling <b>pfnReleasePathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://msdn.microsoft.com/27a03106-a5b5-489c-968a-81b3ea9940cb">pfnAcqirePathInfo</a>



<a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a>



<a href="https://msdn.microsoft.com/9f09ac0e-057c-48fb-a246-35e8ed7ddfc2">pfnAcquireNextPathInfo</a>
 

 

