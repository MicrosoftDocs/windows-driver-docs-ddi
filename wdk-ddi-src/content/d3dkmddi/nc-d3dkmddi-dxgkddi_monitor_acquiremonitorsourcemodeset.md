---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET
title: DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET (d3dkmddi.h)
description: The pfnAcquireMonitorSourceModeSet function returns a handle to the monitor source mode set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_pfnacquiremonitorsourcemodeset.htm
ms.assetid: a64197c0-a61f-4989-9b68-4e06b1a69fd4
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET, DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET callback, VidPnFunctions_b540037c-9f98-4160-aeb3-ded9723e09fa.xml, d3dkmddi/pfnAcquireMonitorSourceModeSet, display.dxgk_monitor_interface_pfnacquiremonitorsourcemodeset, pfnAcquireMonitorSourceModeSet, pfnAcquireMonitorSourceModeSet callback function [Display Devices]
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
 - "d3dkmddi/pfnAcquireMonitorSourceModeSet"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - pfnAcquireMonitorSourceModeSet
product:
 - Windows
---

# DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET callback function

## -description

The <b>pfnAcquireMonitorSourceModeSet</b> function returns a handle to the monitor source mode set object that is associated with a specified monitor.

## -parameters

### -param hAdapter

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param VideoPresentTargetId

[in] An integer that identifies one of the video present targets on the display adapter. The returned source mode set object describes the modes available on the monitor that is connected to this video present target.

### -param phMonitorSourceModeSet

[out] A pointer to a variable that receives a handle to a monitor source mode set object.

### -param ppMonitorSourceModeSetInterface

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitorsourcemodeset_interface">DXGK_MONITORSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor source mode set object.

## -returns

The <b>pfnAcquireMonitorSourceModeSet</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in hAdapter was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The identifier supplied in VideoPresentTargetId was invalid.|
|STATUS_GRAPHICS_MONITOR_NOT_CONNECTED|There is no monitor connected to the video present target identified by VideoPresentTargetId.|

This function might also return other error codes that are defined in <i>Ntstatus.h</i>.

## -remarks

VidPN target identifiers are assigned by the display miniport driver. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a><i></i> function, implemented by the display miniport driver, returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

When you have finished using the monitor source mode set object handle, you must release the handle by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset">pfnReleaseMonitorSourceModeSet</a>. Target mode set objects are reference counted, so if you acquire a handle several times, you must release it that same number of times.

This function is also available in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>

