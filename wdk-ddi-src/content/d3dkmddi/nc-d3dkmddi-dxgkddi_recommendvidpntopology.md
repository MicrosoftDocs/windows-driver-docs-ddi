---
UID: NC:d3dkmddi.DXGKDDI_RECOMMENDVIDPNTOPOLOGY
title: DXGKDDI_RECOMMENDVIDPNTOPOLOGY (d3dkmddi.h)
description: The DxgkDdiRecommendVidPnTopology function creates the topology of a specified VidPN or augments the topology with a new path to video present targets.
old-location: display\dxgkddirecommendvidpntopology.htm
ms.assetid: a7c31d2c-3893-4d25-837d-d4650aeb1cd1
ms.date: 05/10/2018
ms.keywords: DXGKDDI_RECOMMENDVIDPNTOPOLOGY, DXGKDDI_RECOMMENDVIDPNTOPOLOGY callback, DmFunctions_8036db05-72c0-4b67-9151-a33da1df4fb8.xml, DxgkDdiRecommendVidPnTopology, DxgkDdiRecommendVidPnTopology callback function [Display Devices], d3dkmddi/DxgkDdiRecommendVidPnTopology, display.dxgkddirecommendvidpntopology
req.header: d3dkmddi.h
req.include-header: 
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
 - "d3dkmddi/DxgkDdiRecommendVidPnTopology"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkDdiRecommendVidPnTopology
product:
 - Windows
---

# DXGKDDI_RECOMMENDVIDPNTOPOLOGY callback function

## -description

The <i>DxgkDdiRecommendVidPnTopology</i> function creates the topology of a specified VidPN or augments the topology with a new path to video present targets.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pRecommendVidPnTopology

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_recommendvidpntopology">DXGKARG_RECOMMENDVIDPNTOPOLOGY</a> structure that contains function arguments.

## -returns

<i>DxgkDdiRecommendVidPnTopology </i>returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully created or augmented the topology.|
|STATUS_GRAPHICS_NO_RECOMMENDED_VIDPN_TOPOLOGY|The function has no recommendation for the augmentation of the specified VidPN topology.|
|STATUS_GRAPHICS_CANCEL_VIDPN_TOPOLOGY_AUGMENTATION|The function recommends to cancel the augmentation of the specified VidPN's topology on the specified source. This return code is allowed only in the case of VidPN topology augmentation.|
|STATUS_NO_MEMORY|The function failed because it was unable to allocate enough memory.|

The miniport driver should pass through any error code that it gets from the operating system for which it does not have a fallback code path.

## -remarks

<i>DxgkDdiRecommendVidPnTopology</i>
     should be made pageable.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">VidPn Topology Interface</a>

