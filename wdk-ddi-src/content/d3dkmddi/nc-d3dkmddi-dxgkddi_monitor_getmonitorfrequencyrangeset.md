---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET
title: DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET (d3dkmddi.h)
description: The pfnGetMonitorFrequencyRangeSet function returns a handle to the monitor frequency range set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_pfngetmonitorfrequencyrangeset.htm
ms.assetid: 78b80dbb-af1e-457c-854f-ff0404ab9808
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET, DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET callback, VidPnFunctions_2088f146-59a2-49d1-9295-21a28d50e2d0.xml, d3dkmddi/pfnGetMonitorFrequencyRangeSet, display.dxgk_monitor_interface_pfngetmonitorfrequencyrangeset, pfnGetMonitorFrequencyRangeSet, pfnGetMonitorFrequencyRangeSet callback function [Display Devices]
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
- pfnGetMonitorFrequencyRangeSet
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET callback function


## -description


The <b>pfnGetMonitorFrequencyRangeSet</b> function returns a handle to the monitor frequency range set object that is associated with a specified monitor.


## -parameters




### -param hAdapter [in]

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.


### -param VideoPresentTargetId [in]

[in] An integer that identifies one of the video present targets on the display adapter. The returned monitor frequency range set object describes the frequency ranges available on the monitor that is connected to this video present target.


### -param phMonitorFrequencyRangeSet [out]

[out] A pointer to a variable that receives a handle to the monitor frequency range set object.


### -param ppMonitorFrequencyRangeSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitorfrequencyrangeset_interface">DXGK_MONITORFREQUENCYRANGESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor frequency range set object.


## -returns



The <b>pfnGetMonitorFrequencyRangeSet</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER|The handle supplied in hAdapter was invalid.|
|STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET|The identifier supplied in VideoPresentTargetId was invalid.|
|STATUS_GRAPHICS_MONITOR_NOT_CONNECTED|There is no monitor connected to the video present target identified by VideoPresentTargetId.|
 

This function might also return other error codes that are defined in <i>Ntstatus.h</i>.




## -remarks



VidPN target identifiers are assigned by the display miniport driver. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a><i></i><u>function</u>, implemented by the display miniport driver, returns an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgk_child_descriptor">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

You do not need to release the handle returned in <i>phMonitorFrequencyRangeSet</i>.

This function is also available in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgk_monitor_interface_v2">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a>
 

 

