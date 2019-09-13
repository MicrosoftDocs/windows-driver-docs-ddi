---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO (d3dkmddi.h)
description: The pfnCreateNewPathInfo function returns a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that the display miniport driver populates before calling pfnAddPath.
old-location: display\dxgk_vidpntopology_interface_pfncreatenewpathinfo.htm
ms.assetid: 2d9a4e10-514d-4ea9-9d60-0bbb7cdca29d
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO, DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO callback, VidPnFunctions_50591912-0f93-4049-a230-1fc5d96b2132.xml, d3dkmddi/pfnCreateNewPathInfo, display.dxgk_vidpntopology_interface_pfncreatenewpathinfo, pfnCreateNewPathInfo, pfnCreateNewPathInfo callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/pfnCreateNewPathInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnCreateNewPathInfo
product:
 - Windows
---

# DXGKDDI_VIDPNTOPOLOGY_CREATENEWPATHINFO callback function

## -description

The <b>pfnCreateNewPathInfo</b> function returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that the display miniport driver populates before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_addpath">pfnAddPath</a>.

## -parameters

### -param hVidPnTopology

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param ppNewVidPnPresentPathInfo

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure allocated by the VidPN manager.

## -returns

The <b>pfnCreateNewPathInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|

## -remarks

After you call <b>pfnCreateNewPathInfo</b> to obtain a D3DKMDT_VIDPN_PRESENT_PATH structure, you must do one, but not both, of the following:

<ul>
<li>
Populate the structure and pass it to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_addpath">pfnAddPath</a>.

</li>
<li>
Release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a>.

</li>
</ul>
The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_addpath">pfnAddPath</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a>

