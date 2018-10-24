---
UID: NE:d3dkmthk._D3DKMDT_MODE_PRUNING_REASON
title: "_D3DKMDT_MODE_PRUNING_REASON"
author: windows-driver-content
description: The D3DKMDT_MODE_PRUNING_REASON enumeration type contains values that identify the reason why the monitor either supports a display mode or does not support a display mode.
old-location: display\d3dkmdt_mode_pruning_reason.htm
ms.assetid: 41b80b84-3ed6-4ca3-a2ca-63982585d6dc
ms.date: 05/10/2018
ms.keywords: D3DKMDT_MODE_PRUNING_REASON, D3DKMDT_MODE_PRUNING_REASON enumeration [Display Devices], D3DKMDT_MPR_ALLCAPS, D3DKMDT_MPR_CLONE_PATH_PRUNED, D3DKMDT_MPR_DEFAULT_PROFILE_MONITOR_SOURCE_MODE, D3DKMDT_MPR_DESCRIPTOR_MONITOR_FREQUENCY_RANGE, D3DKMDT_MPR_DESCRIPTOR_MONITOR_SOURCE_MODE, D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_FREQUENCY_RANGE, D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_SOURCE_MODE, D3DKMDT_MPR_DRIVER_RECOMMENDED_MONITOR_SOURCE_MODE, D3DKMDT_MPR_MAXVALID, D3DKMDT_MPR_MONITOR_FREQUENCY_RANGE_OVERRIDE, D3DKMDT_MPR_UNINITIALIZED, OpenGL_Structs_e0bd4d47-ff41-4899-8c2a-3738e40ad653.xml, _D3DKMDT_MODE_PRUNING_REASON, d3dkmthk/D3DKMDT_MODE_PRUNING_REASON, d3dkmthk/D3DKMDT_MPR_ALLCAPS, d3dkmthk/D3DKMDT_MPR_CLONE_PATH_PRUNED, d3dkmthk/D3DKMDT_MPR_DEFAULT_PROFILE_MONITOR_SOURCE_MODE, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_MONITOR_FREQUENCY_RANGE, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_MONITOR_SOURCE_MODE, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_FREQUENCY_RANGE, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_SOURCE_MODE, d3dkmthk/D3DKMDT_MPR_DRIVER_RECOMMENDED_MONITOR_SOURCE_MODE, d3dkmthk/D3DKMDT_MPR_MAXVALID, d3dkmthk/D3DKMDT_MPR_MONITOR_FREQUENCY_RANGE_OVERRIDE, d3dkmthk/D3DKMDT_MPR_UNINITIALIZED, display.d3dkmdt_mode_pruning_reason
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMDT_MODE_PRUNING_REASON
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMDT_MODE_PRUNING_REASON
---

# _D3DKMDT_MODE_PRUNING_REASON enumeration


## -description


The D3DKMDT_MODE_PRUNING_REASON enumeration type contains values that identify the reason why the monitor either supports a display mode or does not support a display mode. 


## -enum-fields




### -field D3DKMDT_MPR_UNINITIALIZED

A variable of type D3DKMDT_MODE_PRUNING_REASON has not yet been assigned a meaningful value. 


### -field D3DKMDT_MPR_ALLCAPS

The monitor does not support the display mode because none of the available monitor capabilites imply support of the display mode. 


### -field D3DKMDT_MPR_DESCRIPTOR_MONITOR_SOURCE_MODE

The monitor supports the display mode because of the monitor source mode in the monitor descriptor.


### -field D3DKMDT_MPR_DESCRIPTOR_MONITOR_FREQUENCY_RANGE

The monitor does not support the display mode because of the monitor frequency range in the monitor descriptor. 


### -field D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_SOURCE_MODE

The monitor supports the display mode because of the monitor source mode in the monitor descriptor override. 


### -field D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_FREQUENCY_RANGE

The monitor does not support the display mode because of the monitor frequency range in the monitor descriptor override. 


### -field D3DKMDT_MPR_DEFAULT_PROFILE_MONITOR_SOURCE_MODE

The monitor supports the display mode because of the monitor source mode in the default monitor profile. 


### -field D3DKMDT_MPR_DRIVER_RECOMMENDED_MONITOR_SOURCE_MODE

The monitor supports the display mode because of the monitor source mode that the display miniport driver recommends. 


### -field D3DKMDT_MPR_MONITOR_FREQUENCY_RANGE_OVERRIDE

The monitor supports the display mode because of the monitor frequency range override. 


### -field D3DKMDT_MPR_CLONE_PATH_PRUNED

Supported in Windows 7 and later versions.

The display mode is pruned (that is, the monitor does not support the display mode) because other paths in the clone cluster have no mode supported by the monitor. 


### -field D3DKMDT_MPR_MAXVALID

Valid enumeration values were exceeded. 


## -remarks



The setting of the <b>ValidatedAgainstMonitorCaps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545991">D3DKMDT_DISPLAYMODE_FLAGS</a> structure indicates whether the monitor supports a display mode or not. If the monitor does not support a display mode, the operating system removes the display mode from the list of display modes that are available to the monitor.

When a display mode is supported, the reason type can be one of the following:

<ul>
<li>
D3DKMDT_MPR_DRIVER_RECOMMENDED_MONITOR_SOURCE_MODE

</li>
<li>
D3DKMDT_MPR_DESCRIPTOR_MONITOR_SOURCE_MODE

</li>
<li>
D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_SOURCE_MODE

</li>
<li>
D3DKMDT_MPR_DEFAULT_PROFILE_MONITOR_SOURCE_MODE

</li>
<li>
D3DKMDT_MPR_MONITOR_FREQUENCY_RANGE_OVERRIDE

</li>
</ul>
When a display mode is not supported, the reason type can be one of the following:

<ul>
<li>
D3DKMDT_MPR_DESCRIPTOR_MONITOR_FREQUENCY_RANGE

</li>
<li>
D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_FREQUENCY_RANGE

</li>
<li>
D3DKMDT_MPR_ALLCAPS

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545991">D3DKMDT_DISPLAYMODE_FLAGS</a>
 

 

