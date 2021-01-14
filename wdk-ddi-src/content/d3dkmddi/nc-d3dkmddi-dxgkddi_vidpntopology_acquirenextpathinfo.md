---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO (d3dkmddi.h)
description: The pfnAcquireNextPathInfo function returns a descriptor of the next video present path in a specified VidPN topology, given the current path.
old-location: display\dxgk_vidpntopology_interface_pfnacquirenextpathinfo.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO callback function"]
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO, DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO callback, VidPnFunctions_c06f9c56-bcfd-49a8-a723-4166d7f5129f.xml, d3dkmddi/pfnAcquireNextPathInfo, display.dxgk_vidpntopology_interface_pfnacquirenextpathinfo, pfnAcquireNextPathInfo, pfnAcquireNextPathInfo callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
 - d3dkmddi/DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
product:
 - Windows
---

# DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO callback function


## -description

The <b>pfnAcquireNextPathInfo</b> function returns a descriptor of the next video present path in a specified VidPN topology, given the current path.

## -parameters

### -param hVidPnTopology

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param pVidPnPresentPathInfo

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that describes the current path. The display miniport driver previously obtained this pointer by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo">pfnAcquireFirstPathInfo</a> or <b>pfnAcquireNextPathInfo</b>.

### -param ppNextVidPnPresentPathInfo

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that describes the next path.

## -returns

The <b>pfnAcquireNextPathInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|

## -remarks

When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a>.

You can enumerate all the paths that belong to a VidPN topology object by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo">pfnAcquireFirstPathInfo</a> and then making a sequence of calls to <b>pfnAcquireNextPathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo">pfnAcqirePathInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirefirstpathinfo">pfnAcquireFirstPathInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a>

