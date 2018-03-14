---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO
author: windows-driver-content
description: The pfnReleasePathInfo function releases a D3DKMDT_VIDPN_PRESENT_PATH structure that the VidPN manager previously provided to the display miniport driver.
old-location: display\dxgk_vidpntopology_interface_pfnreleasepathinfo.htm
old-project: display
ms.assetid: fdd34377-6b11-4005-93f1-ab42be7633c2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO, VidPnFunctions_2bbba27c-cbbe-40ea-9ba6-0da2d7d237d5.xml, d3dkmddi/pfnReleasePathInfo, display.dxgk_vidpntopology_interface_pfnreleasepathinfo, pfnReleasePathInfo, pfnReleasePathInfo callback function [Display Devices]
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
-	pfnReleasePathInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO callback


## -description


The <b>pfnReleasePathInfo</b> function releases a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that the VidPN manager previously provided to the display miniport driver.


## -prototype


````
DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO pfnReleasePathInfo;

NTSTATUS APIENTRY pfnReleasePathInfo(
  _In_ const D3DKMDT_HVIDPNTOPOLOGY           hVidPnTopology,
  _In_ const D3DKMDT_VIDPN_PRESENT_PATH CONST *pVidPnPresentPathInfo
)
{ ... }
````


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param pVidPnPresentPathInfo [in]

[in] A pointer to the D3DKMDT_VIDPN_PRESENT_PATH structure that is to be released.


## -returns



The <b>pfnReleasePathInfo</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTopology </i>was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_PRESENT_PATH</b></dt>
</dl>
</td>
<td width="60%">
The pointer supplied in <i>pVidPnPresentPathInfo</i> was invalid.

</td>
</tr>
</table>
 




## -remarks



When you have finished using a D3DKMDT_VIDPN_PRESENT_PATH structure that you obtained by calling any of the following functions, you must release the structure by calling <b>pfnReleasePathInfo</b>.

<ul>
<li>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a>


</li>
<li>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo.md">pfnAcquireNextPathInfo</a>


</li>
<li>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo.md">pfnAcqirePathInfo</a>


</li>
</ul>
If you obtain a D3DKMDT_VIDPN_PRESENT_PATH structure by calling <b><u>pfnCreateNewPathInfo</u></b> and then pass that structure to <b><u>pfnAddPath</u></b>, you do not need to release the structure.

If you obtain a handle by calling <b>pfnCreateNewPathInfo</b> and then you decide not to add the new path to a topology, you must release the newly created structire by calling <b>pfnReleasePathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo.md">pfnAcqirePathInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo.md">pfnAcquireFirstPathInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo.md">pfnAcquireNextPathInfo</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_RELEASEPATHINFO callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

