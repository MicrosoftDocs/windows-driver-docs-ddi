---
UID: NF:winsplp.InitializePrintMonitor
title: InitializePrintMonitor function (winsplp.h)
description: The InitializePrintMonitor function is obsolete and is supported only for compatibility purposes.
old-location: print\initializeprintmonitor.htm
tech.root: print
ms.assetid: 825ae98b-74d7-4e41-944b-0dc77cc0cc51
ms.date: 04/20/2018
ms.keywords: InitializePrintMonitor, InitializePrintMonitor function [Print Devices], print.initializeprintmonitor, spoolfnc_ff45a3d4-a007-4ebd-b120-582f23ccaffb.xml, winsplp/InitializePrintMonitor
ms.topic: function
f1_keywords:
 - "winsplp/InitializePrintMonitor"
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
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
- InitializePrintMonitor
product:
- Windows
targetos: Windows
req.typenames: 
---

# InitializePrintMonitor function


## -description


The <b>InitializePrintMonitor</b> function is obsolete and is supported only for compatibility purposes. New print monitors should implement <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitor2">InitializePrintMonitor2</a> so that they can be used with print server clusters.

A print monitor's <b>InitializePrintMonitor</b> function initializes a print monitor.


## -parameters




### -param pRegistryRoot [in]

Caller-supplied pointer to a string identifying a registry path that the print monitor can use to store monitor-specific values.


## -returns



If the operation succeeds, the function should return a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorex">MONITOREX</a> structure. Otherwise the function should call SetLastError (described in the Microsoft Windows SDK documentation) to set an error code, and return <b>NULL</b>.




## -remarks



The <b>InitializePrintMonitor</b> function must be exported by <a href="https://docs.microsoft.com/windows-hardware/drivers/print/language-monitors">language monitors</a> and by port monitor server DLLs. The function is called immediately after the monitor DLL is loaded, and is not called again until the DLL is reloaded. Its purposes are to allow the monitor to initialize itself, and to provide the spooler with pointers to internal monitor functions. Function pointers are contained in a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/modem/ff542552(v=vs.85)">MONITOR</a> structure, which is referenced through the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorex">MONITOREX</a> function.

The <i>pRegistryRoot</i> parameter supplies a pointer a string representing the path to a <i>MonitorName</i> registry key, where <i>MonitorName</i> is the monitor name that was specified when the spooler's <b>AddMonitor</b> function was called to add the monitor. The monitor can use this key to store monitor-specific value names and values. When the spooler's <b>DeleteMonitor</b> function is called, the spooler deletes the <i>MonitorName</i> key and all values stored underneath it. (The <b>AddMonitor</b> and <b>DeleteMonitor</b> functions are described in the Windows SDK documentation.)




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/nf-winsplp-initializeprintmonitorui">InitializePrintMonitorUI</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winsplp/ns-winsplp-_monitorex">MONITOREX</a>
 

 

