---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH
title: DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH (d3dkmddi.h)
description: The pfnRemovePath function removes a video present path to a specified VidPN topology object.
old-location: display\dxgk_vidpntopology_interface_pfnremovepath.htm
ms.assetid: 463973e0-c443-417a-86ff-0b78773d40cc
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH, DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH callback, VidPnFunctions_0a43b9cf-d4c2-4d6f-acc7-7988038c56e5.xml, d3dkmddi/pfnRemovePath, display.dxgk_vidpntopology_interface_pfnremovepath, pfnRemovePath, pfnRemovePath callback function [Display Devices]
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
 - "d3dkmddi/pfnRemovePath"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnRemovePath
product:
 - Windows
---

# DXGKDDI_VIDPNTOPOLOGY_REMOVEPATH callback function

## -description

The <b>pfnRemovePath</b> function removes a video present path to a specified VidPN topology object.

## -parameters

### -param hVidPnTopology

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_gettopology">pfnGetTopology</a> function of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param VidPnSourceId

[in] An integer that identifies a VidPN source path.

### -param VidPnTargetId

[in] An integer that identifies a VidPN target path.

## -returns

The <b>pfnRemovePath</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The specified video present path has been successfully removed from this VidPN topology object.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE|The VidPN source identifier supplied in VidPnSourceId is invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The VidPN target identifier supplied in VidPnTargetId is invalid.|
|STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY|The handle supplied in hVidPnTopology is invalid.|
|STATUS_ACCESS_DENIED|The path cannot be removed in the context of the current DDI call.|

## -remarks

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in<i> D3dkmdt.h</i>.

