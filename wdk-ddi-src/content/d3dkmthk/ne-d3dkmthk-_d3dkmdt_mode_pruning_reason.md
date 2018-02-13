---
UID: NE:d3dkmthk._D3DKMDT_MODE_PRUNING_REASON
title: "_D3DKMDT_MODE_PRUNING_REASON"
author: windows-driver-content
description: The D3DKMDT_MODE_PRUNING_REASON enumeration type contains values that identify the reason why the monitor either supports a display mode or does not support a display mode.
old-location: display\d3dkmdt_mode_pruning_reason.htm
old-project: display
ms.assetid: 41b80b84-3ed6-4ca3-a2ca-63982585d6dc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_SOURCE_MODE, D3DKMDT_MPR_CLONE_PATH_PRUNED, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_MONITOR_SOURCE_MODE, D3DKMDT_MPR_ALLCAPS, D3DKMDT_MPR_MONITOR_FREQUENCY_RANGE_OVERRIDE, d3dkmthk/D3DKMDT_MPR_DEFAULT_PROFILE_MONITOR_SOURCE_MODE, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_MONITOR_FREQUENCY_RANGE, display.d3dkmdt_mode_pruning_reason, d3dkmthk/D3DKMDT_MPR_CLONE_PATH_PRUNED, d3dkmthk/D3DKMDT_MPR_ALLCAPS, d3dkmthk/D3DKMDT_MPR_MONITOR_FREQUENCY_RANGE_OVERRIDE, D3DKMDT_MPR_MAXVALID, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_SOURCE_MODE, d3dkmthk/D3DKMDT_MPR_UNINITIALIZED, D3DKMDT_MPR_DEFAULT_PROFILE_MONITOR_SOURCE_MODE, _D3DKMDT_MODE_PRUNING_REASON, d3dkmthk/D3DKMDT_MPR_MAXVALID, d3dkmthk/D3DKMDT_MPR_DRIVER_RECOMMENDED_MONITOR_SOURCE_MODE, D3DKMDT_MPR_UNINITIALIZED, D3DKMDT_MODE_PRUNING_REASON enumeration [Display Devices], OpenGL_Structs_e0bd4d47-ff41-4899-8c2a-3738e40ad653.xml, D3DKMDT_MPR_DESCRIPTOR_MONITOR_FREQUENCY_RANGE, d3dkmthk/D3DKMDT_MODE_PRUNING_REASON, D3DKMDT_MPR_DESCRIPTOR_MONITOR_SOURCE_MODE, D3DKMDT_MODE_PRUNING_REASON, d3dkmthk/D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_FREQUENCY_RANGE, D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_FREQUENCY_RANGE, D3DKMDT_MPR_DRIVER_RECOMMENDED_MONITOR_SOURCE_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMDT_MODE_PRUNING_REASON
product: Windows
targetos: Windows
req.typenames: D3DKMDT_MODE_PRUNING_REASON
---

# _D3DKMDT_MODE_PRUNING_REASON enumeration


## -description


The D3DKMDT_MODE_PRUNING_REASON enumeration type contains values that identify the reason why the monitor either supports a display mode or does not support a display mode. 


## -syntax


````
typedef enum _D3DKMDT_MODE_PRUNING_REASON { 
  D3DKMDT_MPR_UNINITIALIZED                                = 0,
  D3DKMDT_MPR_ALLCAPS                                      = 1,
  D3DKMDT_MPR_DESCRIPTOR_MONITOR_SOURCE_MODE               = 2,
  D3DKMDT_MPR_DESCRIPTOR_MONITOR_FREQUENCY_RANGE           = 3,
  D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_SOURCE_MODE      = 4,
  D3DKMDT_MPR_DESCRIPTOR_OVERRIDE_MONITOR_FREQUENCY_RANGE  = 5,
  D3DKMDT_MPR_DEFAULT_PROFILE_MONITOR_SOURCE_MODE          = 6,
  D3DKMDT_MPR_DRIVER_RECOMMENDED_MONITOR_SOURCE_MODE       = 7,
  D3DKMDT_MPR_MONITOR_FREQUENCY_RANGE_OVERRIDE             = 8,
  D3DKMDT_MPR_CLONE_PATH_PRUNED                            = 9,
  D3DKMDT_MPR_MAXVALID                                     = 10
} D3DKMDT_MODE_PRUNING_REASON;
````


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



The setting of the <b>ValidatedAgainstMonitorCaps</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmdt_displaymode_flags.md">D3DKMDT_DISPLAYMODE_FLAGS</a> structure indicates whether the monitor supports a display mode or not. If the monitor does not support a display mode, the operating system removes the display mode from the list of display modes that are available to the monitor.

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmdt_displaymode_flags.md">D3DKMDT_DISPLAYMODE_FLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_MODE_PRUNING_REASON enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

