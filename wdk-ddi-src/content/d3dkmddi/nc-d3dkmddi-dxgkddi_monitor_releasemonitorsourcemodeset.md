---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET
title: DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET (d3dkmddi.h)
description: The pfnReleaseMonitorSourceModeSet function releases a handle to a monitor source mode set object.
old-location: display\dxgk_monitor_interface_pfnreleasemonitorsourcemodeset.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET callback function"]
ms.keywords: DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET, DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET callback, VidPnFunctions_5f8e1fd8-b807-4da2-901e-0284e21d858e.xml, d3dkmddi/pfnReleaseMonitorSourceModeSet, display.dxgk_monitor_interface_pfnreleasemonitorsourcemodeset, pfnReleaseMonitorSourceModeSet, pfnReleaseMonitorSourceModeSet callback function [Display Devices]
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
 - DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET
 - d3dkmddi/DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnReleaseMonitorSourceModeSet
product:
 - Windows
---

# DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET callback function


## -description

The <b>pfnReleaseMonitorSourceModeSet</b> function releases a handle to a monitor source mode set object.

## -parameters

### -param hAdapter

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param hMonitorSourceModeSet

[in] The handle to be released.

## -returns

The <b>pfnReleaseMonitorSourceModeSet</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in *hAdapter* was invalid.|
|STATUS_INVALID_MONITOR_SOURCEMODESET|The handle supplied in *hMonitorSourceModeSet* was invalid.|


This function might also return other error codes that are defined in <i>Ntstatus.h</i>.

## -remarks

When you have finished using a handle that you obtained by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset">pfnAcquireMonitorSourceModeSet</a>, you must release the handle by calling <b>pfnReleaseMonitorSourceModeSet</b>.

This function is also available in the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>
