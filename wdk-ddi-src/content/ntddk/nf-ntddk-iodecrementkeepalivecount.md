---
UID: NF:ntddk.IoDecrementKeepAliveCount
title: IoDecrementKeepAliveCount function
author: windows-driver-content
description: The IoDecrementKeepAliveCount routine decrements a reference count associated with an Windows app on a specific device.
old-location: kernel\iodecrementkeepalivecount.htm
old-project: kernel
ms.assetid: 2A8BC777-291C-4EC4-8EF9-AA78C6295700
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoDecrementKeepAliveCount routine [Kernel-Mode Driver Architecture], ntddk/IoDecrementKeepAliveCount, kernel.iodecrementkeepalivecount, IoDecrementKeepAliveCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Ntoskrnl.exe
apiname:
-	IoDecrementKeepAliveCount
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoDecrementKeepAliveCount function


## -description


The <b>IoDecrementKeepAliveCount</b> routine decrements a reference count associated with an Windows app on a specific device. This routine is called by a kernel mode driver when the app's I/O process has completed.  If the app's reference count drops to 0, Windows can suspend the app.


## -syntax


````
NTSTATUS IoDecrementKeepAliveCount(
  _Inout_           FileObject,
  _Inout_ PEPROCESS Process
);
````


## -parameters




### -param FileObject [in, out]

The file object handle to the device.


### -param Process [in, out]

The process associated with the device.


## -returns


This routine returns <b>STATUS_SUCCESS</b> on success, or the appropriate <b>NTSTATUS</b> error code on failure. <b>NTSTATUS</b> error codes are defined in Ntstatus.h.


