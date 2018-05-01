---
UID: NS:d3dkmddi._DXGK_MONITOR_INTERFACE
title: "_DXGK_MONITOR_INTERFACE"
author: windows-driver-content
description: The DXGK_MONITOR_INTERFACE structure contains pointers to functions that belong to the Monitor Interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitor_interface.htm
old-project: display
ms.assetid: edb6df63-7354-4da3-b641-2ce7f28ca7e8
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGK_MONITOR_INTERFACE, DXGK_MONITOR_INTERFACE structure [Display Devices], DmStructs_23906e50-4f65-4483-a54c-915f9fd3c433.xml, _DXGK_MONITOR_INTERFACE, d3dkmddi/DXGK_MONITOR_INTERFACE, display.dxgk_monitor_interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MONITOR_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MONITOR_INTERFACE
---

# _DXGK_MONITOR_INTERFACE structure


## -description


The DXGK_MONITOR_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor Interface</a>, which is implemented by the video present network (VidPN) manager.


## -struct-fields




### -field Version

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561979">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that indicates the monitor interface version. Must be set to 1.


### -field pfnAcquireMonitorSourceModeSet

A pointer to the <a href="https://msdn.microsoft.com/a64197c0-a61f-4989-9b68-4e06b1a69fd4">pfnAcquireMonitorSourceModeSet</a> function.


### -field pfnReleaseMonitorSourceModeSet

A pointer to the <a href="https://msdn.microsoft.com/af5f4a1b-232c-4192-96b4-8fa31dfe3019">pfnReleaseMonitorSourceModeSet</a> function.


### -field pfnGetMonitorFrequencyRangeSet

A pointer to the <a href="https://msdn.microsoft.com/78b80dbb-af1e-457c-854f-ff0404ab9808">pfnGetMonitorFrequencyRangeSet</a> function.


### -field pfnGetMonitorDescriptorSet

A pointer to the <a href="https://msdn.microsoft.com/e2244cd3-6630-440b-a4f7-1e0fa5702161">pfnGetMonitorDescriptorSet</a> function.


## -remarks



<div class="alert"><b>Note</b>    A display miniport driver must verify the interface version specified in the <b>Version</b> member before using <p class="note">this structure.

</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561968">DXGK_MONITOR_INTERFACE_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561979">DXGK_MONITOR_INTERFACE_VERSION</a>
 

 

