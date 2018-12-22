---
UID: NS:winsplp._MONITOR2
title: "_MONITOR2"
description: The MONITOR2 structure contains pointers to the functions defined by print monitors.
old-location: print\monitor2.htm
tech.root: print
ms.assetid: 0bfb5119-2034-4e63-9fbe-e2ff42a352d6
ms.date: 04/20/2018
ms.keywords: "*LPMONITOR2, *PMONITOR2, LPMONITOR2, LPMONITOR2 structure pointer [Print Devices], MONITOR2, MONITOR2 structure [Print Devices], PMONITOR2, PMONITOR2 structure pointer [Print Devices], _MONITOR2, print.monitor2, spoolfnc_db4ec1e7-1368-4695-bae0-91fd5dcd8a1a.xml, winsplp/LPMONITOR2, winsplp/MONITOR2, winsplp/PMONITOR2"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	MONITOR2
product:
- Windows
targetos: Windows
req.typenames: MONITOR2, *PMONITOR2, *LPMONITOR2
---

# _MONITOR2 structure


## -description


The MONITOR2 structure contains pointers to the functions defined by print monitors.


## -struct-fields




### -field cbSize

Specifies the size, in bytes, of the MONITOR2 structure.


### -field pfnEnumPorts

A port monitor server DLL's <b>EnumPorts</b> function enumerates the ports that the port monitor supports.


### -field pfnOpenPort

Pointer to the print monitor's <b>OpenPort</b> function.


### -field pfnOpenPortEx

A language monitor's <code>OpenPortEx</code> function opens a printer port.


### -field pfnStartDocPort

A print monitor's <code>StartDocPort</code> function performs the tasks required to start a print job on the specified port.


### -field pfnWritePort

Pointer to the print monitor's <b>WritePort</b> function.


### -field pfnReadPort

Pointer to the print monitor's <b>ReadPort</b> function.


### -field pfnEndDocPort

A print monitor's <b>EndDocPort</b> function performs the tasks required to end a print job on the specified port.


### -field pfnClosePort

Pointer to the print monitor's <b>ClosePort</b> function.


### -field pfnAddPort

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> function is obsolete and is for use only with Windows NT 4.0 and previous versions.


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545022">AddPort</a> creates a port and adds it to the list of ports currently supported by the specified monitor in the spooler environment.


### -field pfnAddPortEx

(Obsolete. Must be <b>NULL</b>.) Pointer to the print monitor's <b>AddPortEx</b> function. (Port monitors only.)


### -field pfnConfigurePort

The <b>ConfigurePort</b> function is obsolete and is for use only with Windows NT 4.0 and previous versions. For later versions of Windows, use <b>ConfigurePortUI</b>.

<b>ConfigurePort</b> is a port management function that configures the specified port.


### -field pfnDeletePort

The <b>DeletePort</b> function is obsolete and is for use only with Windows NT 4.0 and previous versions.

<b>DeletePort</b> deletes a port from the monitor's environment.


### -field pfnGetPrinterDataFromPort

Pointer to the print monitor's <b>GetPrinterDataFromPort</b> function.


### -field pfnSetPortTimeOuts

A port monitor server DLL's <code>SetPortTimeOuts</code> function sets port time-out values for an open port.


### -field pfnXcvOpenPort

Pointer to the print monitor's <b>XcvOpenPort</b> function. (Port monitors only.)


### -field pfnXcvDataPort

Pointer to the print monitor's <b>XcvDataPort</b> function. (Port monitors only.)


### -field pfnXcvClosePort

Pointer to the print monitor's <b>XcvClosePort</b> function. (Port monitors only.)


### -field pfnShutdown

Pointer to the print monitor's <b>Shutdown</b> function.


### -field pfnSendRecvBidiDataFromPort

Pointer to the print monitor's <b>SendRecvBidiDataFromPort</b> function.


### -field pfnNotifyUsedPorts

 


### -field pfnNotifyUnusedPorts

 


### -field pfnPowerEvent

 




## -remarks



Each language monitor and each port monitor server DLL must provide a MONITOR2 structure. The monitor must supply values for all structure members, and specify the structure's address as the return value for its <a href="https://msdn.microsoft.com/library/windows/hardware/ff551605">InitializePrintMonitor2</a> function.

If a function is not defined, its pointer must be <b>NULL</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551605">InitializePrintMonitor2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557541">MONITORUI</a>
 

 

