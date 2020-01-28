---
UID: NF:winsplp.XcvClosePort
title: XcvClosePort function (winsplp.h)
description: A port monitor server DLL's XcvClosePort function closes a printer port that was opened by XcvOpenPort.
old-location: print\xcvcloseport.htm
tech.root: print
ms.assetid: 8dfeb2d5-e75e-4e5b-b209-cb23133136f7
ms.date: 02/02/2018
ms.keywords: XcvClosePort, winsplp/XcvClosePort, print.xcvcloseport, spoolfnc_5d0750d1-1f50-4e09-8c91-1362b2037265.xml, XcvClosePort function [Print Devices]
f1_keywords:
 - "winsplp/XcvClosePort"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winsplp.h
api_name:
- XcvClosePort
product:
- Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# XcvClosePort function


## -description


A port monitor server DLL's <code>XcvClosePort</code> function closes a printer port that was opened by <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>.


## -syntax


```cpp
BOOL XcvClosePort(
  _In_ HANDLE hXcv
);
```


## -parameters




### -param hXcv [in]

Caller-supplied printer handle obtained by calling <b>OpenPrinter</b> (described in the Microsoft Windows SDK documentation). This handle is created and returned by <a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.




## -remarks



Port monitor server DLLs are required to define an <code>XcvClosePort</code> function and include its address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The spooler's <b>ClosePrinter</b> function calls <code>XcvClosePort</code> if the printer name that was specified with a previous call to the <b>OpenPrinter</b> function included either of the strings "XcvPort" or "XcvMonitor". For more information, see <a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>. For more information about the <b>OpenPrinter</b> and <b>ClosePrinter</b> functions, see the Windows SDK documentation.

The function should close the port specified by the handle, and it should make the handle invalid.




## -see-also

<a href="..\winsplp\nf-winsplp-xcvopenport.md">XcvOpenPort</a>



<a href="..\winsplp\nf-winsplp-addportui.md">AddPortUI</a>



 

 


