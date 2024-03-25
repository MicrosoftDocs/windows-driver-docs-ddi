---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET (d3dkmddi.h)
description: Learn more about the pfnGetAdditionalMonitorModeSet function.
ms.date: 06/09/2023
keywords: ["DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback function"]
ms.keywords: DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET, DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback, VidPnFunctions_c86b07fb-c73c-4990-86a0-15c93ba7e2dd.xml, d3dkmddi/pfnGetAdditionalMonitorModeSet, display.dxgk_monitor_interface_v2_pfngetadditionalmonitormodeset, pfnGetAdditionalMonitorModeSet, pfnGetAdditionalMonitorModeSet callback function [Display Devices]
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
 - DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
 - d3dkmddi/DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
---

# DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback function

## -description

The **pfnGetAdditionalMonitorModeSet** function returns a handle to an additional monitor source mode set object that is associated with a specified monitor. It is available in the [**DXGK_MONITOR_INTERFACE_V2**](ns-d3dkmddi-_dxgk_monitor_interface_v2.md) interface, starting in Windows 7.

## -parameters

### -param hAdapter [in]

A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the **DxgkInterface** parameter of the [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param VideoPresentTargetId [in]

An integer that identifies one of the video present targets on the display adapter. The returned **ppAdditionalModesSet** additional modes set object describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.

### -param pNumberModes [out]

A pointer to a variable that contains the number of additional timing modes of the video present target specified by **VideoPresentTargetId**.

### -param ppAdditionalModesSet [out]

A pointer to a variable that receives a pointer to a [**DXGK_TARGETMODE_DETAIL_TIMING**](../d3dkmdt/ns-d3dkmdt-_dxgk_targetmode_detail_timing.md) structure. The structure describes a video present target's additional timing modes that are compatible with the display device.

## -returns

The [**pfnAcquireMonitorSourceModeSet**](nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md) function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in hAdapter was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The identifier supplied in VideoPresentTargetId was invalid.|
|STATUS_GRAPHICS_MONITOR_NOT_CONNECTED|There is no monitor connected to the video present target identified by VideoPresentTargetId.|
|STATUS_NOT_FOUND|The video present target identified by VideoPresentTargetId could not be found.|

## -remarks

VidPN target identifiers are assigned by the display miniport driver. The [**DxgkDdiQueryChildRelations**](../dispmprt/nc-dispmprt-dxgkddi_query_child_relations.md) function, implemented by the display miniport driver, returns an array of [**DXGK_CHILD_DESCRIPTOR**](../dispmprt/ns-dispmprt-_dxgk_child_descriptor.md) structures, each of which contains an identifier.

This function is available beginning with Windows 7.

## -see-also

[**DXGK_CHILD_DESCRIPTOR**](../dispmprt/ns-dispmprt-_dxgk_child_descriptor.md)

[**DXGK_MONITOR_INTERFACE_V2**](ns-d3dkmddi-_dxgk_monitor_interface_v2.md)

[**DXGK_MONITOR_INTERFACE_V2::pfnReleaseAdditionalMonitorModeSet**](nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset.md)

[**DXGK_TARGETMODE_DETAIL_TIMING**](../d3dkmdt/ns-d3dkmdt-_dxgk_targetmode_detail_timing.md)

[**DxgkDdiQueryChildRelations**](../dispmprt/nc-dispmprt-dxgkddi_query_child_relations.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
