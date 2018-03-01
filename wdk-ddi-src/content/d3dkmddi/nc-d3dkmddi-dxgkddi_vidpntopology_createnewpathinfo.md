---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO
author: windows-driver-content
description: The pfnCreateNewPathInfo function returns a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that the display miniport driver populates before calling pfnAddPath.
old-location: display\dxgk_vidpntopology_interface_pfncreatenewpathinfo.htm
old-project: display
ms.assetid: 2d9a4e10-514d-4ea9-9d60-0bbb7cdca29d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO, VidPnFunctions_50591912-0f93-4049-a230-1fc5d96b2132.xml, d3dkmddi/pfnCreateNewPathInfo, display.dxgk_vidpntopology_interface_pfncreatenewpathinfo, pfnCreateNewPathInfo, pfnCreateNewPathInfo callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
-	pfnCreateNewPathInfo
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO callback


## -description


The <b>pfnCreateNewPathInfo</b> function returns a pointer to a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that the display miniport driver populates before calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_addpath.md">pfnAddPath</a>.


## -prototype


````
DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO pfnCreateNewPathInfo;

NTSTATUS APIENTRY pfnCreateNewPathInfo(
  _In_  const D3DKMDT_HVIDPNSOURCEMODESET hVidPnTopology,
  _Out_       D3DKMDT_VIDPN_PRESENT_PATH  **ppNewVidPnPresentPathInfo
)
{ ... }
````


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_gettopology.md">pfnGetTopology</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.


### -param ppNewVidPnPresentPathInfo [out]

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure allocated by the VidPN manager.


## -returns



The <b>pfnCreateNewPathInfo</b> function returns one of the following values:

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
</table>
 




## -remarks



After you call <b>pfnCreateNewPathInfo</b> to obtain a D3DKMDT_VIDPN_PRESENT_PATH structure, you must do one, but not both, of the following:

<ul>
<li>
Populate the structure and pass it to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_addpath.md">pfnAddPath</a>.

</li>
<li>
Release the structure by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>.

</li>
</ul>
The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_addpath.md">pfnAddPath</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo.md">pfnReleasePathInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

