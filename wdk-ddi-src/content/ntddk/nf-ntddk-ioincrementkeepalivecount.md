---
UID: NF:ntddk.IoIncrementKeepAliveCount
title: IoIncrementKeepAliveCount function (ntddk.h)
description: The IoIncrementKeepAliveCount routine increments a reference count associated with an Windows app process on a specific device.
old-location: kernel\ioincrementkeepalivecount.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoIncrementKeepAliveCount function"]
ms.keywords: IoIncrementKeepAliveCount, IoIncrementKeepAliveCount routine [Kernel-Mode Driver Architecture], kernel.ioincrementkeepalivecount, ntddk/IoIncrementKeepAliveCount
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IoIncrementKeepAliveCount
 - ntddk/IoIncrementKeepAliveCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - IoIncrementKeepAliveCount
---

# IoIncrementKeepAliveCount function


## -description

The <b>IoIncrementKeepAliveCount</b> routine increments a reference count associated with an Windows app process on a specific device. This routine is called by a kernel mode driver in response to the app opening a process for I/O. This prevents Windows from suspending the app before the I/O process is complete.

## -parameters

### -param FileObject 

[in, out]
The file object handle to the device.

### -param Process 

[in, out]
The process associated with the device.

## -returns

This routine returns <b>STATUS_SUCCESS</b> on success, or the appropriate <b>NTSTATUS</b> error code on failure. <b>NTSTATUS</b> error codes are defined in Ntstatus.h.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iodecrementkeepalivecount">IoDecrementKeepAliveCount</a>
