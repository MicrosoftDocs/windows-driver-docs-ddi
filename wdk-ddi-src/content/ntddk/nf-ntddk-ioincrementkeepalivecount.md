---
UID: NF:ntddk.IoIncrementKeepAliveCount
title: IoIncrementKeepAliveCount function
author: windows-driver-content
description: The IoIncrementKeepAliveCount routine increments a reference count associated with an Windows app process on a specific device.
old-location: kernel\ioincrementkeepalivecount.htm
old-project: kernel
ms.assetid: A80754BD-0F23-4EE9-898F-30743AA82C72
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoIncrementKeepAliveCount, IoIncrementKeepAliveCount routine [Kernel-Mode Driver Architecture], kernel.ioincrementkeepalivecount, ntddk/IoIncrementKeepAliveCount
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	IoIncrementKeepAliveCount
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoIncrementKeepAliveCount function


## -description


The <b>IoIncrementKeepAliveCount</b> routine increments a reference count associated with an Windows app process on a specific device. This routine is called by a kernel mode driver in response to the app opening a process for I/O. This prevents Windows from suspending the app before the I/O process is complete.


## -parameters




### -param FileObject [in, out]

The file object handle to the device.


### -param Process [in, out]

The process associated with the device.


## -returns



This routine returns <b>STATUS_SUCCESS</b> on success, or the appropriate <b>NTSTATUS</b> error code on failure. <b>NTSTATUS</b> error codes are defined in Ntstatus.h.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780273">IoDecrementKeepAliveCount</a>
 

 

