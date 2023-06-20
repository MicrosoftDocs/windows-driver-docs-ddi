---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET (d3dkmddi.h)
description: Learn more about the pfnReleaseAdditionalMonitorModeSet function.
ms.date: 06/09/2023
keywords: ["DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback function"]
ms.keywords: DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET, DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback, VidPnFunctions_7b298754-19ed-420f-88f9-2910c3f5968a.xml, d3dkmddi/pfnReleaseAdditionalMonitorModeSet, display.dxgk_monitor_interface_v2_pfnreleaseadditionalmonitormodeset, pfnReleaseAdditionalMonitorModeSet, pfnReleaseAdditionalMonitorModeSet callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 7
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
 - DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
 - d3dkmddi/DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
product:
 - Windows
---

# DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback function

## -description

The **pfnReleaseAdditionalMonitorModeSet** function releases a handle to an additional monitor source mode set object that is associated with a specified monitor. It is available in the [**DXGK_MONITOR_INTERFACE_V2**](ns-d3dkmddi-_dxgk_monitor_interface_v2.md) interface, starting in Windows 7.

## -parameters

### -param hAdapter [in]

A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the **DxgkInterface** parameter of the [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param VideoPresentTargetId [in]

An integer that identifies one of the video present targets on the display adapter. The additional modes set object **ppAdditionalModesSet** returned in a call to the [**pfnGetAdditionalMonitorModeSet**](nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md) function describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.

### -param pAdditionalModesSet [in]

A pointer to a variable that receives a [**DXGK_TARGETMODE_DETAIL_TIMING**](../d3dkmdt/ns-d3dkmdt-_dxgk_targetmode_detail_timing.md) structure that describes a video present target's additional timing modes that are compatible with the display device. This structure was initially obtained in a call to [**pfnGetAdditionalMonitorModeSet**](nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md).

## -returns

The **pfnReleaseAdditionalMonitorModeSet** function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in hAdapter was invalid.|
|STATUS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in ppAdditionalModesSet was invalid.|

## -remarks

This function is available beginning with Windows 7.

## -see-also

[**DXGK_MONITOR_INTERFACE_V2**](ns-d3dkmddi-_dxgk_monitor_interface_v2.md)

[**DXGK_MONITOR_INTERFACE_V2::pfnGetAdditionalMonitorModeSet**](nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
