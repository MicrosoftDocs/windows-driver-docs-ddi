---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ADDPATH
title: DXGKDDI_VIDPNTOPOLOGY_ADDPATH (d3dkmddi.h)
description: The pfnAddPath function adds a video present path to a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnaddpath.htm
ms.assetid: 893e0be1-aa29-429a-a3ca-a9f19053fd92
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ADDPATH, DXGKDDI_VIDPNTOPOLOGY_ADDPATH callback, VidPnFunctions_9c594989-a5f6-4977-8a1b-0302d30e8df7.xml, d3dkmddi/pfnAddPath, display.dxgk_vidpntopology_interface_pfnaddpath, pfnAddPath, pfnAddPath callback function [Display Devices]
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
 - "d3dkmddi/pfnAddPath"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAddPath
product:
 - Windows
---

# DXGKDDI_VIDPNTOPOLOGY_ADDPATH callback function

## -description

The <b>pfnAddPath</b> function adds a video present path to a specified VidPN topology object.

## -parameters

### -param hVidPnTopology

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param pVidPnPresentPath

[in] A pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that describes the path. The display miniport driver previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo">pfnCreateNewPathInfo</a>.

## -returns

The <b>pfnAddPath</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|
|STATUS_ACCESS_DENIED|The path cannot be removed in the context of the current DDI call.|

## -remarks

To add a path to a topology, the display miniport driver performs the following steps.

Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo">pfnCreateNewPathInfo</a> to obtain a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a> structure allocated by the VidPN manager.

Populate the D3DKMDT_VIDPN_PRESENT_PATH structure with information about the path, including video present source and target identifiers.

Call <b>pfnAddPath</b> to add the path to a topology. 

The VidPN manager allocates a D3DKMDT_VIDPN_PRESENT_PATH structure when you call <b>pfnCreateNewPathInfo</b>. If you add the path described by that structure to a topology, then you do not need to explicitly release the structure; <b>pfnAddPath</b> releases it.

If you obtain a D3DKMDT_VIDPN_PRESENT_PATH structure by calling <b>pfnCreateNewPathInfo</b> and then decide not to add that path to a topology, then you must explicity release the structure by calling <b>pfnReleasePathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in<i> D3dkmdt.h</i>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_present_path">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_createnewpathinfo">pfnCreateNewPathInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_releasepathinfo">pfnReleasePathInfo</a>

