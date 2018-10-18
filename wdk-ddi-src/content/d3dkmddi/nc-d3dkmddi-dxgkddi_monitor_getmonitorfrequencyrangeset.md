---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET
title: DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET
author: windows-driver-content
description: The pfnGetMonitorFrequencyRangeSet function returns a handle to the monitor frequency range set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_pfngetmonitorfrequencyrangeset.htm
ms.assetid: 78b80dbb-af1e-457c-854f-ff0404ab9808
ms.date: 5/10/2018
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnGetMonitorFrequencyRangeSet
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

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -param VideoPresentTargetId [in]

[in] An integer that identifies one of the video present targets on the display adapter. The returned monitor frequency range set object describes the frequency ranges available on the monitor that is connected to this video present target.


### -param phMonitorFrequencyRangeSet [out]

[out] A pointer to a variable that receives a handle to the monitor frequency range set object.


### -param ppMonitorFrequencyRangeSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561904">DXGK_MONITORFREQUENCYRANGESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor frequency range set object.


## -returns



The <b>pfnGetMonitorFrequencyRangeSet</b> function returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hAdapter</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_TARGET</b></dt>
</dl>
</td>
<td width="60%">
The identifier supplied in <i>VideoPresentTargetId</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_MONITOR_NOT_CONNECTED</b></dt>
</dl>
</td>
<td width="60%">
There is no monitor connected to the video present target identified by <i>VideoPresentTargetId</i>.

</td>
</tr>
</table>
 

This function might also return other error codes that are defined in <i>Ntstatus.h</i>.




## -remarks



VidPN target identifiers are assigned by the display miniport driver. The <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a><i></i><u>function</u>, implemented by the display miniport driver, returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

You do not need to release the handle returned in <i>phMonitorFrequencyRangeSet</i>.

This function is also available in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561968">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561968">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>
 

 

