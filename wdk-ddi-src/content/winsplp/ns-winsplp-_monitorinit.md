---
UID: NS:winsplp._MONITORINIT
title: _MONITORINIT (winsplp.h)
description: The MONITORINIT structure is used as an input parameter to a print monitor's InitializePrintMonitor2 function.
old-location: print\monitorinit.htm
tech.root: print
ms.assetid: 3445997f-a607-4071-b05e-c1a8d01892b2
ms.date: 04/20/2018
keywords: ["_MONITORINIT structure"]
ms.keywords: "*PMONITORINIT, MONITORINIT, MONITORINIT structure [Print Devices], PMONITORINIT, PMONITORINIT structure pointer [Print Devices], _MONITORINIT, print.monitorinit, spoolfnc_321f67a1-b279-4909-af99-d3e564bf3555.xml, winsplp/MONITORINIT, winsplp/PMONITORINIT"
f1_keywords:
 - "winsplp/MONITORINIT"
req.header: winsplp.h
req.include-header: Winsplp.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winsplp.h
api_name:
- MONITORINIT
product:
- Windows
targetos: Windows
req.typenames: MONITORINIT, *PMONITORINIT
---

# _MONITORINIT structure


## -description


The MONITORINIT structure is used as an input parameter to a print monitor's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitor2">InitializePrintMonitor2</a> function.


## -struct-fields




### -field cbSize

Size, in bytes, of the MONITORINIT structure.


### -field hSpooler

Spooler handle, for use as input to functions identified by the MONITORREG structure.


### -field hckRegistryRoot

Registry handle, for use as input to functions identified by the MONITORREG structure.


### -field pMonitorReg

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorreg">MONITORREG</a> structure.


### -field bLocal

<b>TRUE</b> if the monitor is being called by a local node spooler. <b>FALSE</b> if the monitor is being called by a cluster spooler. (Monitors can usually ignore this member.)


### -field pszServerName

Caller-supplied pointer to a string representing a server name.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitor2">InitializePrintMonitor2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorreg">MONITORREG</a>
 

 

