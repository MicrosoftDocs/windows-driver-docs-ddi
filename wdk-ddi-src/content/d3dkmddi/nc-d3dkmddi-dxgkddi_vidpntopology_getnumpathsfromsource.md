---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE
title: DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE (d3dkmddi.h)
description: The pfnGetNumPathsFromSource function returns the number of video present paths that contain a specified video present source.
old-location: display\dxgk_vidpntopology_interface_pfngetnumpathsfromsource.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE callback function"]
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE, DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE callback, VidPnFunctions_6c0bd823-4803-474c-9948-22282c5b1e66.xml, d3dkmddi/pfnGetNumPathsFromSource, display.dxgk_vidpntopology_interface_pfngetnumpathsfromsource, pfnGetNumPathsFromSource, pfnGetNumPathsFromSource callback function [Display Devices]
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
 - DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE
 - d3dkmddi/DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnGetNumPathsFromSource
product:
 - Windows
---

# DXGKDDI_VIDPNTOPOLOGY_GETNUMPATHSFROMSOURCE callback function


## -description

The <b>pfnGetNumPathsFromSource</b> function returns the number of video present paths that contain a specified video present source.

## -parameters

### -param hVidPnTopology

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param VidPnSourceId

[in] An integer that identifies a particular video present source.

### -param pNumPathsFromSource

[out] A pointer to a SIZE_T-typed variable that receives the number of paths that contain the specified source.

## -returns

The <b>pfnGetNumPathsFromSource</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|
|STATUS_INVALID_PARAMETER|The pointer supplied in pNumPathsFromSource was in valid.|

## -remarks

A topology is a collection paths, each of which contains a (source, target) pair. It is possible for a particular source to appear in more than one path. For example, one source can be paired with two distinct targets in the case of a clone view.

VidPN source identifiers are assigned by the operating system. <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

The D3DDDI_VIDEO_PRESENT_SOURCE_ID data type is defined in <i>D3dukmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_getnumpaths">pfnGetNumPaths</a>
