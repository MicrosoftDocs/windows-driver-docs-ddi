---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET
title: DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET
description: The pfnGetMonitorDescriptorSet function returns a handle to a monitor descriptor set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_pfngetmonitordescriptorset.htm
ms.assetid: e2244cd3-6630-440b-a4f7-1e0fa5702161
ms.date: 05/10/2018
ms.keywords: DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET, DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET callback, VidPnFunctions_3d364729-f0d7-4bba-a71b-08d9c56499d7.xml, d3dkmddi/pfnGetMonitorDescriptorSet, display.dxgk_monitor_interface_pfngetmonitordescriptorset, pfnGetMonitorDescriptorSet, pfnGetMonitorDescriptorSet callback function [Display Devices]
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
-	pfnGetMonitorDescriptorSet
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET callback function


## -description


The <b>pfnGetMonitorDescriptorSet</b> function returns a handle to a monitor descriptor set object that is associated with a specified monitor.


## -parameters




### -param hAdapter [in]

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -param VideoPresentTargetId [in]

[in] An integer that identifies one of the video present targets on the display adapter. The returned monitor descriptor set object contains descriptors for the monitor that is connected to this video present target.


### -param phMonitorDescriptorSet [out]

[out] A pointer to a variable that receives a handle to a monitor descriptor set object.


### -param ppMonitorDescriptorSetInterface [out]

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561886">DXGK_MONITORDESCRIPTORSET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the monitor descriptor set object.


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



VidPN target identifiers are assigned by the display miniport driver. The <a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a> function, implemented by the display miniport driver, returns an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structures, each of which contains an identifier.

You do not need to release the handle returned in <i>phMonitorDescriptorSet</i>.

This function is also available in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561968">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561968">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>
 

 

