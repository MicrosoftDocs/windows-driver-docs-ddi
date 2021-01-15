---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET
title: DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET (d3dkmddi.h)
description: The pfnGetMonitorDescriptorSet function returns a handle to a monitor descriptor set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_pfngetmonitordescriptorset.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET callback function"]
ms.keywords: DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET, DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET callback, VidPnFunctions_3d364729-f0d7-4bba-a71b-08d9c56499d7.xml, d3dkmddi/pfnGetMonitorDescriptorSet, display.dxgk_monitor_interface_pfngetmonitordescriptorset, pfnGetMonitorDescriptorSet, pfnGetMonitorDescriptorSet callback function [Display Devices]
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
 - DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET
 - d3dkmddi/DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET
product:
 - Windows
---

# DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET callback function


## -description

The <b>pfnGetMonitorDescriptorSet</b> function returns a handle to a monitor descriptor set object that is associated with a specified monitor.

## -parameters

### -param hAdapter

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param VideoPresentTargetId

[in] An integer that identifies one of the video present targets on the display adapter. The returned monitor descriptor set object contains descriptors for the monitor that is connected to this video present target.

### -param phMonitorDescriptorSet

[out] A pointer to a variable that receives a handle to a monitor descriptor set object.

### -param ppMonitorDescriptorSetInterface

[out] A pointer to a variable that receives a pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitordescriptorset_interface">DXGK_MONITORDESCRIPTORSET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor descriptor set object.

## -returns

The <b>pfnGetMonitorDescriptorSet</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in hAdapter was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The identifier supplied in VideoPresentTargetId was invalid.|
|STATUS_GRAPHICS_MONITOR_NOT_CONNECTED|There is no monitor connected to the video present target identified by VideoPresentTargetId.|

## -remarks

VidPN target identifiers are assigned by the display miniport driver. The <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, returns an array of <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

You do not need to release the handle returned in <i>phMonitorDescriptorSet</i>.

This function is also available in the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>

