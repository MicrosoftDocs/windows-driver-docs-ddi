---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO (d3dkmddi.h)
description: The pfnAcquireFirstPathInfo structure returns a descriptor of the first path in a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnacquirefirstpathinfo.htm
ms.assetid: b5dc35dc-f4fb-4209-9a4d-50dc11f16216
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO, DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO callback, VidPnFunctions_d45dd9b3-775b-41a6-a5e4-8fb226ed7ea4.xml, d3dkmddi/pfnAcquireFirstPathInfo, display.dxgk_vidpntopology_interface_pfnacquirefirstpathinfo, pfnAcquireFirstPathInfo, pfnAcquireFirstPathInfo callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/pfnAcquireFirstPathInfo"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireFirstPathInfo
product:
 - Windows
---

# DXGKDDI_VIDPNTOPOLOGY_ACQUIREFIRSTPATHINFO callback function

## -description

The <b>pfnAcquireFirstPathInfo</b> structure returns a descriptor of the first path in a specified VidPN topology object.

## -parameters

### -param hVidPnTopology

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param ppFirstVidPnPresentPathInfo

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure. The structure contains a variety of information about the path, including the path's source and target identifiers.

## -returns

The <b>pfnAcquireFirstPathInfo</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|

## -remarks

When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a>.

You can enumerate all the paths that belong to a VidPN topology object by calling <b>pfnAcquireFirstPathInfo</b> and then making a sequence of calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo">pfnAcquireNextPathInfo</a>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirepathinfo">pfnAcqirePathInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_acquirenextpathinfo">pfnAcquireNextPathInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a>

