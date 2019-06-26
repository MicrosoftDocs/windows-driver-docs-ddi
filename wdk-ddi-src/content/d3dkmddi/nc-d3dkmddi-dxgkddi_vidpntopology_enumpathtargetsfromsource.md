---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE
title: DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE (d3dkmddi.h)
description: The pfnEnumPathTargetsFromSource function returns the identifier of one of the video present targets associated with a specified video present source.
old-location: display\dxgk_vidpntopology_interface_pfnenumpathtargetsfromsource.htm
ms.assetid: ca925b3c-8141-419d-99a1-43764ec07315
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE, DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE callback, VidPnFunctions_1d5b570a-a3c6-444f-884f-cbd7228f64c9.xml, d3dkmddi/pfnEnumPathTargetsFromSource, display.dxgk_vidpntopology_interface_pfnenumpathtargetsfromsource, pfnEnumPathTargetsFromSource, pfnEnumPathTargetsFromSource callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- pfnEnumPathTargetsFromSource
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTOPOLOGY_ENUMPATHTARGETSFROMSOURCE callback function


## -description


The <b>pfnEnumPathTargetsFromSource</b> function returns the identifier of one of the video present targets associated with a specified video present source.


## -parameters




### -param hVidPnTopology [in]

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.


### -param VidPnSourceId [in]

[in] An integer that identifies a particular video present source.


### -param VidPnPresentPathIndex [in]

[in] A zero-based index into the set of paths that contain the source identified by <i>VidPnSourceId</i>.


### -param pVidPnTargetId [out]

[out] A pointer to a variable that receives the target identifier.


## -returns



The <b>pfnEnumPathTargetsFromSource</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology was invalid.|
|STATUS_INVALID_PARAMETER|The pointer supplied in pVidPnTargetId was in valid.|


## -remarks



<i>VidPnPresentPathIndex</i> is not an index into the set of all paths in the topology identified by <i>hVidPnTopology</i>. It is an index into a subset of all the paths in the topology: specifically, the subset of all paths that contain the source identified by <i>VidPnSourceId</i>.

To enumerate (in a given topology) all the targets associated with a particular source, perform the following steps.

Call <b>pfnGetNumPathsFromSource</b> to determine the number N of paths that contain the source of interest. Think of those paths as an indexed set with indices 0, 1, ... N - 1.

For each index 0 though N - 1, pass the source identifier and the index to <b>pfnEnumPathTargetsFromSource</b>.

A topology is a collection paths, each of which contains a (source, target) pair. It is possible for a particular source to appear in more than one path. For example, one source can be paired with two distinct targets in the case of a clone view.

VidPN source identifiers are assigned by the operating system. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>, implemented by the display miniport driver, returns the number N of video present sources supported by the display adapter. Then the operating system assigns identifiers 0, 1, 2, ... N - 1.

VidPN target identifiers are assigned by the display miniport driver. <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>, implemented by the display miniport driver, returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

The D3DKMDT_HVIDPNTOPOLOGY and D3DKMDT_VIDPN_PRESENT_PATH_INDEX data types are defined in <i>D3dkmdt.h</i>.  

The D3DDDI_VIDEO_PRESENT_SOURCE_ID and D3DDDI_VIDEO_PRESENT_TARGET_ID data types are defined in <i>D3dukmdt.h</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_getnumpathsfromsource">pfnGetNumPathsFromSource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntopology_getpathsourcefromtarget">pfnGetPathSourceFromTarget</a>
 

 

