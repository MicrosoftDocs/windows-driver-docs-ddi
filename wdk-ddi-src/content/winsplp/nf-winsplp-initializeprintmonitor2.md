---
UID: NF:winsplp.InitializePrintMonitor2
title: InitializePrintMonitor2 function
author: windows-driver-content
description: A print monitor's InitializePrintMonitor2 function initializes a print monitor for use with clustered print servers.
old-location: print\initializeprintmonitor2.htm
old-project: print
ms.assetid: 73348405-0cc1-412a-b9b1-cfcc300190d7
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: InitializePrintMonitor2
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
req.alt-api: InitializePrintMonitor2
req.alt-loc: winsplp.h
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
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# InitializePrintMonitor2 function



## -description
A print monitor's <b>InitializePrintMonitor2</b> function initializes a print monitor for use with clustered print servers.



## -syntax

````
LPMONITOR2 InitializePrintMonitor2(
  _In_  PMONITORINIT pMonitorInit,
  _Out_ PHANDLE      phMonitor
);
````


## -parameters

### -param pMonitorInit [in]

Caller-supplied pointer to a <a href="..\winsplp\ns-winsplp-_monitorinit.md">MONITORINIT</a> structure.


### -param phMonitor [out]

Caller-supplied location in which the function returns a monitor handle.


## -returns
If the operation succeeds, the function should return a pointer to a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure. Otherwise the function should call SetLastError (described in the Microsoft Windows SDK documentation) to set an error code, and return <b>NULL</b>.


## -remarks
The <b>InitializePrintMonitor2</b> function must be exported by <a href="https://msdn.microsoft.com/26ba1c22-390a-4187-b67a-3f3497964f8e">language monitors</a> and by port monitor server DLLs. The function is called immediately after the monitor DLL is loaded, and is not called again until the DLL is reloaded. Its purposes are to allow the monitor to initialize itself, and to provide the spooler with pointers to internal monitor functions. Function pointers are contained in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure is larger in Windows XP than it was in Windows 2000. In order to ensure that a monitor developed with the Windows XP Driver Development Kit (DDK) will install on Windows XP and Windows 2000, the monitor must do the following:

Perform a run-time check to determine which operating system version the monitor is running on.

If the monitor is running on Windows 2000, it must set the <b>cbSize</b> member of the MONITOR2 structure to MONITOR2_SIZE_WIN2K (defined in Winsplp.h), the size appropriate for Windows 2000 version of this structure.

The following function determines whether the current operating system version is Windows 2000.

For a monitor that is loading on Windows 2000, the following code sets the MONITOR2 structure's <b>cbSize</b> member appropriately.


## -see-also
<dl>
<dt>
<a href="..\winsplp\ns-winsplp-_monitorinit.md">MONITORINIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20InitializePrintMonitor2 function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

