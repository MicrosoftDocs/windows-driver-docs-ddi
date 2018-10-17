---
UID: NF:winsplp.ClosePort
title: ClosePort function
author: windows-driver-content
description: A language or port monitor's ClosePort function closes a printer port.
old-location: print\closeport.htm
tech.root: print
ms.assetid: 1d63f36d-4c62-40e9-b3c0-f6d847340b07
ms.date: 2/2/2018
ms.keywords: print.closeport, winsplp/ClosePort, spoolfnc_fdd98daa-d14c-4534-a8c6-0070ccbbc3fe.xml, ClosePort, ClosePort function [Print Devices]
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
-	ClosePort
product:
- Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# ClosePort function


## -description


A language or port monitor's <b>ClosePort</b> function closes a printer port.


## -syntax


```
BOOL ClosePort(
  _In_ HANDLE hPort
);
```


## -parameters




### -param hPort [in]

Caller-supplied pointer to a port handle.


## -returns



If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.




## -remarks




<a href="https://msdn.microsoft.com/26ba1c22-390a-4187-b67a-3f3497964f8e">Language monitors</a> and port monitor server DLLs are required to define a <b>ClosePort</b> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The handle received as the function's <i>hPort</i> argument is the port handle that the monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559596">OpenPortEx</a> function supplied.

The <b>ClosePort</b> function should close the port by making the received port handle invalid. It should also free all system resources that were allocated by the monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559596">OpenPortEx</a> function.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559596">OpenPortEx</a>



<a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a>



<a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a>



 

 


