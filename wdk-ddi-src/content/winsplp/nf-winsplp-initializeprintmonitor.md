---
UID: NF:winsplp.InitializePrintMonitor
title: InitializePrintMonitor function
author: windows-driver-content
description: The InitializePrintMonitor function is obsolete and is supported only for compatibility purposes.
old-location: print\initializeprintmonitor.htm
old-project: print
ms.assetid: 825ae98b-74d7-4e41-944b-0dc77cc0cc51
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: InitializePrintMonitor, winsplp/InitializePrintMonitor, InitializePrintMonitor function [Print Devices], print.initializeprintmonitor, spoolfnc_ff45a3d4-a007-4ebd-b120-582f23ccaffb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winsplp.h
apiname:
-	InitializePrintMonitor
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# InitializePrintMonitor function


## -description


The <b>InitializePrintMonitor</b> function is obsolete and is supported only for compatibility purposes. New print monitors should implement <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> so that they can be used with print server clusters.

A print monitor's <b>InitializePrintMonitor</b> function initializes a print monitor.


## -syntax


````
LPMONITOREX InitializePrintMonitor(
  _In_ LPWSTR pRegistryRoot
);
````


## -parameters




### -param pRegistryRoot [in]

Caller-supplied pointer to a string identifying a registry path that the print monitor can use to store monitor-specific values.


## -returns


If the operation succeeds, the function should return a pointer to a <a href="..\winsplp\ns-winsplp-_monitorex.md">MONITOREX</a> structure. Otherwise the function should call SetLastError (described in the Microsoft Windows SDK documentation) to set an error code, and return <b>NULL</b>.



## -remarks


The <b>InitializePrintMonitor</b> function must be exported by <a href="https://msdn.microsoft.com/26ba1c22-390a-4187-b67a-3f3497964f8e">language monitors</a> and by port monitor server DLLs. The function is called immediately after the monitor DLL is loaded, and is not called again until the DLL is reloaded. Its purposes are to allow the monitor to initialize itself, and to provide the spooler with pointers to internal monitor functions. Function pointers are contained in a <a href="..\winsplp\ns-winsplp-_monitor.md">MONITOR</a> structure, which is referenced through the <a href="..\winsplp\ns-winsplp-_monitorex.md">MONITOREX</a> function.

The <i>pRegistryRoot</i> parameter supplies a pointer a string representing the path to a <i>MonitorName</i> registry key, where <i>MonitorName</i> is the monitor name that was specified when the spooler's <b>AddMonitor</b> function was called to add the monitor. The monitor can use this key to store monitor-specific value names and values. When the spooler's <b>DeleteMonitor</b> function is called, the spooler deletes the <i>MonitorName</i> key and all values stored underneath it. (The <b>AddMonitor</b> and <b>DeleteMonitor</b> functions are described in the Windows SDK documentation.)



## -see-also

<a href="..\winsplp\ns-winsplp-_monitorex.md">MONITOREX</a>

<a href="..\winsplp\nf-winsplp-initializeprintmonitorui.md">InitializePrintMonitorUI</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20InitializePrintMonitor function%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

