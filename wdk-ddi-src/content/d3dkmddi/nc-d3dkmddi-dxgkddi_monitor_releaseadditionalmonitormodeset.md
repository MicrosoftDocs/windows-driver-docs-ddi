---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET (d3dkmddi.h)
description: The pfnReleaseAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, releases a handle to an additional monitor source mode set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_v2_pfnreleaseadditionalmonitormodeset.htm
ms.assetid: b9f6cb52-8870-4319-a1ff-d3dbbeef8cb6
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback function"]
ms.keywords: DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET, DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback, VidPnFunctions_7b298754-19ed-420f-88f9-2910c3f5968a.xml, d3dkmddi/pfnReleaseAdditionalMonitorModeSet, display.dxgk_monitor_interface_v2_pfnreleaseadditionalmonitormodeset, pfnReleaseAdditionalMonitorModeSet, pfnReleaseAdditionalMonitorModeSet callback function [Display Devices]
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
 - "d3dkmddi/pfnReleaseAdditionalMonitorModeSet"
 - "pfnReleaseAdditionalMonitorModeSet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnReleaseAdditionalMonitorModeSet
product:
 - Windows
---

# DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback function

## -description

The <b>pfnReleaseAdditionalMonitorModeSet</b> function, available in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7, releases a handle to an additional monitor source mode set object that is associated with a specified monitor.

## -parameters

### -param hAdapter

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param VideoPresentTargetId

[in] An integer that identifies one of the video present targets on the display adapter. The additional modes set object <i>ppAdditionalModesSet</i> returned in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset">pfnGetAdditionalMonitorModeSet</a> function describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.

### -param pAdditionalModesSet

[in] A pointer to a variable that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgk_targetmode_detail_timing">DXGK_TARGETMODE_DETAIL_TIMING</a> structure that describes a video present target's additional timing modes that are compatible with the display device. This structure was initially obtained in a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset">pfnGetAdditionalMonitorModeSet</a>.

## -returns

The <b>pfnReleaseAdditionalMonitorModeSet</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in hAdapter was invalid.|
|STATUS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in ppAdditionalModesSet was invalid.|

## -remarks

This function is available beginning with Windows 7.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset">DXGK_MONITOR_INTERFACE_V2::pfnGetAdditionalMonitorModeSet</a>

