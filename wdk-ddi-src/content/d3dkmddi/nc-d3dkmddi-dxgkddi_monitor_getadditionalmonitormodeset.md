---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET
author: windows-driver-content
description: The pfnGetAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, returns a handle to an additional monitor source mode set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_v2_pfngetadditionalmonitormodeset.htm
old-project: display
ms.assetid: 37878f3a-f61e-423c-ab03-94318089f7af
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET, VidPnFunctions_c86b07fb-c73c-4990-86a0-15c93ba7e2dd.xml, d3dkmddi/pfnGetAdditionalMonitorModeSet, display.dxgk_monitor_interface_v2_pfngetadditionalmonitormodeset, pfnGetAdditionalMonitorModeSet, pfnGetAdditionalMonitorModeSet callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnGetAdditionalMonitorModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDI_MONITOR_GETADDITIONALMONITORMODESET callback


## -description


The <i>pfnGetAdditionalMonitorModeSet</i> function, available in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561968">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7, returns a handle to an additional monitor source mode set object that is associated with a specified monitor.


## -parameters




### -param hAdapter [in]

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -param VideoPresentTargetId [in]

[in] An integer that identifies one of the video present targets on the display adapter. The returned <i>ppAdditionalModesSet</i> additional modes set object describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.


### -param pNumberModes [out]

[out] A pointer to a variable that contains the number of additional timing modes of the video present target specified by <i>VideoPresentTargetId</i>.


### -param ppAdditionalModesSet [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562060">DXGK_TARGETMODE_DETAIL_TIMING</a> structure. The structure describes a video present target's additional timing modes that are compatible with the display device.


## -returns



The <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function returns one of the following values.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The video present target identified by <i>VideoPresentTargetId</i> could not be found.

</td>
</tr>
</table>
 




## -remarks



VidPN target identifiers are assigned by the display miniport driver. The <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

This function is available beginning with Windows 7.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561968">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://msdn.microsoft.com/b9f6cb52-8870-4319-a1ff-d3dbbeef8cb6">DXGK_MONITOR_INTERFACE_V2::pfnReleaseAdditionalMonitorModeSet</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562060">DXGK_TARGETMODE_DETAIL_TIMING</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>
 

 

