---
UID: NF:winsplp.WritePort
title: WritePort function (winsplp.h)
description: A port monitor's WritePort function writes data to a printer port.
old-location: print\writeport.htm
tech.root: print
ms.assetid: 31229c78-0bea-44eb-9f1a-d1bce8a16a3e
ms.date: 02/02/2018
keywords: ["WritePort function"]
ms.keywords: print.writeport, WritePort, winsplp/WritePort, WritePort function [Print Devices], spoolfnc_b4300d7a-1424-40e0-931f-08c727eb4174.xml
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
 - WritePort
 - winsplp/WritePort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - WritePort
---

# WritePort function


## -description

A port monitor's <code>WritePort</code> function writes data to a printer port.

## -parameters

### -param hPort 

[in]
Caller-supplied port handle.

### -param pBuffer 

[in]
Caller-supplied pointer to a buffer containing data to be written to the port.

### -param cbBuf

Caller-supplied size, in bytes, of <i>pBuffer</i>.

### -param pcbWritten 

[out]
Caller-supplied pointer to a location to receive the number of bytes successfully written to the port.

## -returns

If the operation succeeds, the function should return <b>TRUE</b>. Otherwise it should return <b>FALSE</b>.

## -syntax

```cpp
BOOL WritePort(
  _In_  HANDLE  hPort,
  _In_  LPBYTE  pBuffer,
        DWORD   cbBuf,
  _Out_ LPDWORD pcbWritten
);
```

## -remarks

<a href="https://docs.microsoft.com/windows-hardware/drivers/print/language-monitors">Language monitors</a> and port monitor server DLLs are required to define a <code>WritePort</code> function and include the function's address in a <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> structure.

The handle received as the function's <i>hPort</i> argument is the port handle that the monitor's <a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a> or <a href="https://docs.microsoft.com/previous-versions/ff559596(v=vs.85)">OpenPortEx</a> function supplied.

Typically, a language monitor's <code>WritePort</code> function adds language-specific commands to the data stream contained in the buffer pointed to by <i>pBuffer</i>, and then passes the modified data stream to the port monitor's <code>WritePort</code> function.

A port monitor server DLL's <code>WritePort</code> function usually calls <b>WriteFile</b> (described in the Microsoft Windows SDK documentation) to send the data stream to the kernel-mode port driver.

A typical print job consists of multiple calls to <code>WritePort</code>. Each call can have a different <i>cbBuf</i> value.

The function should return the number of bytes successfully written by placing the number in the location pointed to by <i>pcbWritten</i>. For language monitors, this number must not include the number of extra, language-specific bytes added to the data stream.

The spooler determines the success or failure of the write operation by checking <code>WritePort</code>'s return value, not the returned byte count. So a returned byte count of zero does not represent a failed write unless the function returns <b>FALSE</b>.

Some sort of system-implemented or monitor-implemented time-out mechanism must ensure that the <code>WritePort</code> function will return within a reasonable amount of time, to avoid stalling the spooler.

It is acceptable for a language monitor to call a port monitor's <code>WritePort</code> routine outside of a <a href="https://docs.microsoft.com/previous-versions/ff562710(v=vs.85)">StartDocPort</a>/<a href="https://docs.microsoft.com/previous-versions/ff548742(v=vs.85)">EndDocPort</a> pair. However, some port monitors might fail such a call, so the language monitor must be written to handle this failure.

## -see-also

<a href="https://docs.microsoft.com/previous-versions/ff562710(v=vs.85)">StartDocPort</a>



<a href="https://docs.microsoft.com/previous-versions/ff559596(v=vs.85)">OpenPortEx</a>



<a href="..\winsplp\nf-winsplp-openport.md">OpenPort</a>



<a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a>



<a href="https://docs.microsoft.com/previous-versions/ff548742(v=vs.85)">EndDocPort</a>

