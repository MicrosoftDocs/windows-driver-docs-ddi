---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO
title: DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO
author: windows-driver-content
description: The pfnUpdatePathSupportInfo function updates the transformation and copy protection support of a particular path in a specified VidPN topology.
old-location: display\dxgk_vidpntopology_interface_pfnupdatepathsupportinfo.htm
ms.assetid: affe9ab2-49ef-4284-b441-49c311158827
ms.date: 5/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO, DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO callback, VidPnFunctions_6944a007-1a0a-41fc-b137-92307c532cca.xml, d3dkmddi/pfnUpdatePathSupportInfo, display.dxgk_vidpntopology_interface_pfnupdatepathsupportinfo, pfnUpdatePathSupportInfo, pfnUpdatePathSupportInfo callback function [Display Devices]
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
-	pfnUpdatePathSupportInfo
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTOPOLOGY_UPDATEPATHSUPPORTINFO callback function


## -description


The <b>pfnUpdatePathSupportInfo</b> function updates the transformation and copy protection support of a particular path in a specified VidPN topology.


## -parameters




### -param i_hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param i_pVidPnPresentPathInfo [in]

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The <b>VidPnSourceId</b> and <b>VidPnTargetId</b> members (taken as a pair) identify the path that is to have its transformation and copy protection support updated. The <b>ContentTransformation</b> and <b>CopyProtection</b> members supply the updated transformation and copy protection support.


## -returns



The <b>pfnUpdatePathSupportInfo</b> function returns one of the following values.

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
<dt><b>STATUS_GRAPHICS_INVALID_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>i_hVidPnTopology</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The path cannot be removed in the context of the current DDI call.

</td>
</tr>
</table>
 




## -remarks



The display miniport driver's <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a> function calls <b>pnfUpdatePathSupportInfo</b> to report rotation, scaling, and copy protection support for each of the paths in a topology.



