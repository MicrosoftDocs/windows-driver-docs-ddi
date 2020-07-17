---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET (d3dkmddi.h)
description: The pfnGetAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, returns a handle to an additional monitor source mode set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_v2_pfngetadditionalmonitormodeset.htm
ms.assetid: 37878f3a-f61e-423c-ab03-94318089f7af
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback function"]
ms.keywords: DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET, DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback, VidPnFunctions_c86b07fb-c73c-4990-86a0-15c93ba7e2dd.xml, d3dkmddi/pfnGetAdditionalMonitorModeSet, display.dxgk_monitor_interface_v2_pfngetadditionalmonitormodeset, pfnGetAdditionalMonitorModeSet, pfnGetAdditionalMonitorModeSet callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
 - "d3dkmddi/pfnGetAdditionalMonitorModeSet"
 - "pfnGetAdditionalMonitorModeSet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnGetAdditionalMonitorModeSet
product:
 - Windows
---

# DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback function

## -description

The <i>pfnGetAdditionalMonitorModeSet</i> function, available in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7, returns a handle to an additional monitor source mode set object that is associated with a specified monitor.

## -parameters

### -param hAdapter

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param VideoPresentTargetId

[in] An integer that identifies one of the video present targets on the display adapter. The returned <i>ppAdditionalModesSet</i> additional modes set object describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.

### -param pNumberModes

[out] A pointer to a variable that contains the number of additional timing modes of the video present target specified by <i>VideoPresentTargetId</i>.

### -param ppAdditionalModesSet

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_targetmode_detail_timing">DXGK_TARGETMODE_DETAIL_TIMING</a> structure. The structure describes a video present target's additional timing modes that are compatible with the display device.

## -returns

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in hAdapter was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The identifier supplied in VideoPresentTargetId was invalid.|
|STATUS_GRAPHICS_MONITOR_NOT_CONNECTED|There is no monitor connected to the video present target identified by VideoPresentTargetId.|
|STATUS_NOT_FOUND|The video present target identified by VideoPresentTargetId could not be found.|

## -remarks

VidPN target identifiers are assigned by the display miniport driver. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

This function is available beginning with Windows 7.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_releaseadditionalmonitormodeset">DXGK_MONITOR_INTERFACE_V2::pfnReleaseAdditionalMonitorModeSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_targetmode_detail_timing">DXGK_TARGETMODE_DETAIL_TIMING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>

