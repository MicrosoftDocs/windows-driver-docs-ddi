---
UID: NF:winsplp.OpenPort
title: OpenPort function (winsplp.h)
description: A port monitor's OpenPort function opens a printer port.
old-location: print\openport.htm
tech.root: print
ms.assetid: 32e47d3a-83ad-4d3f-a6ce-c03712021844
ms.date: 02/02/2018
keywords: ["OpenPort function"]
ms.keywords: spoolfnc_94948c6d-fab4-44ce-9650-72464d5e3fdf.xml, pfnOpenPort, print.openport, OpenPort, pfnOpenPort function [Print Devices], winsplp/pfnOpenPort
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
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
f1_keywords:
 - OpenPort
 - winsplp/OpenPort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - pfnOpenPort
---

# OpenPort function


## -description

A port monitor's <code>OpenPort</code> function opens a printer port.

## -parameters

### -param pName

Caller-supplied pointer to a string containing the name of the port to be opened.

### -param pHandle

Caller-supplied pointer to a location to receive a port handle.


#### - hMonitor

Caller supplied monitor instance handle. This is the handle returned by the monitor's <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> function. (This parameter does not exist if the print monitor supports <b>InitializePrintMonitor</b> instead of <b>InitializePrintMonitor2</b>.)

## -returns

If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.

## -syntax

```cpp
BOOL WINAPI pfnOpenPort(
   HANDLE  hMonitor,
   LPWSTR  pName,
   PHANDLE pHandle
);
```

## -remarks

Port monitor server DLLs are required to define an <code>OpenPort</code> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The <code>OpenPort</code> function is called, either by a language monitor or by the print spooler, when a print queue is being connected to a port. The <code>OpenPort</code> function's primary purpose is to return a port handle that the caller can use as an input argument for subsequent calls to the port monitor's <a href="https://docs.microsoft.com/previous-versions/ff562710(v=vs.85)">StartDocPort</a>, <a href="..\winsplp\nf-winsplp-writeport.md">WritePort</a>, <a href="..\winsplp\nf-winsplp-readport.md">ReadPort</a>, <a href="https://docs.microsoft.com/previous-versions/ff548742(v=vs.85)">EndDocPort</a>, and <a href="https://docs.microsoft.com/previous-versions/ff550506(v=vs.85)">GetPrinterDataFromPort</a> functions.

Besides returning a port handle, the <code>OpenPort</code> function can perform initialization operations that need to be taken care of before read or write operations are performed. For example, if the port supports modifiable time-out values, the <code>OpenPort</code> function should set these values.

Calls to <code>OpenPort</code> are not print job-specific. Between each call to a port monitor's <code>OpenPort</code> and <a href="..\winsplp\nf-winsplp-closeport.md">ClosePort</a> functions, there can be multiple calls to its <b>StartDocPort</b> and <b>EndDocPort</b> functions.

You can assume that after the print spooler has called <code>OpenPort</code> with a particular port name, it will not call <code>OpenPort</code> again with the same port name before calling <b>ClosePort</b>.

Print monitor functions that accept a port handle as input do not also accept a monitor handle. Therefore, the <code>OpenPort</code> function must store the received monitor handle in a location that can be referenced by the port handle. This allows the functions that accept a port handle to reference the monitor handle.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff550506(v=vs.85)">GetPrinterDataFromPort</a>



<a href="https://docs.microsoft.com/previous-versions/ff562630(v=vs.85)">SetPortTimeOuts</a>



<a href="..\winsplp\nf-winsplp-closeport.md">ClosePort</a>



<a href="https://docs.microsoft.com/previous-versions/ff562710(v=vs.85)">StartDocPort</a>



<a href="https://docs.microsoft.com/previous-versions/ff559596(v=vs.85)">OpenPortEx</a>



<a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a>



<a href="..\winsplp\nf-winsplp-writeport.md">WritePort</a>



<a href="https://docs.microsoft.com/previous-versions/ff548742(v=vs.85)">EndDocPort</a>



<a href="..\winsplp\nf-winsplp-readport.md">ReadPort</a>

