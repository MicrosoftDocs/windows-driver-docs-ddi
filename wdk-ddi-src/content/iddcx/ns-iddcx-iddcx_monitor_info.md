---
UID: NS:iddcx.IDDCX_MONITOR_INFO
title: IDDCX_MONITOR_INFO
author: windows-driver-content
description: Gives information about the current monitor and its connection type.
old-location: display\iddcx_monitor_info.htm
old-project: display
ms.assetid: 62c2182c-af55-4482-a890-803f92dc863a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.iddcx_monitor_info, IDDCX_MONITOR_INFO, iddcx/IDDCX_MONITOR_INFO, IDDCX_MONITOR_INFO structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
-	iddcx.h
apiname:
-	IDDCX_MONITOR_INFO
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_MONITOR_INFO structure


## -description


Gives information about the current monitor and its connection type.
             


## -syntax


````
typedef struct IDDCX_MONITOR_INFO {
  UINT                                  Size;
  DISPLAYCONFIG_VIDEO_OUTPUT_TECHNOLOGY MonitorType;
  UINT                                  ConnectorIndex;
  IDDCX_MONITOR_DESCRIPTION             MonitorDescription;
  GUID                                  MonitorContainerId;
} IDDCX_MONITOR_INFO, *IDDCX_MONITOR_INFO;
````


## -struct-fields




### -field Size


                     Total size of the structure
                 


### -field MonitorType

The monitor connector type of the monitor
                 


### -field ConnectorIndex


                     This is a zero-based unique identifier for this connector. It should be unique for this adapter and the value should not change for this connector across system reboot or driver upgrade. 

<div class="alert"><b>Note</b>  The value has to be between 0 and the <a href="..\iddcx\ns-iddcx-iddcx_adapter_caps.md">IDDCX_ADAPTER_CAPS</a> value MaxMonitorsSupported minus 1.
                 </div>
<div> </div>

### -field MonitorDescription


                     Pointer to the monitor description for the monitor. If the monitor does not have any description data, this should be set to NULL
                 


### -field MonitorContainerId


                     Container Id of the monitor being connected. If any device is also inside the monitor (eg audio, touch etc), then those devices should all have the same container id.
                 

