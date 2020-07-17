---
UID: NF:ntddk.IoSetActivityIdThread
title: IoSetActivityIdThread function (ntddk.h)
description: The IoSetActivityIdThread routine associates an activity ID with the current thread. Drivers should use this routine when they are tracing aware and are issuing I/O on a worker thread.
old-location: kernel\iosetactivityidthread.htm
tech.root: kernel
ms.assetid: 4C7884AB-C763-4FAF-8799-E0113B3F3AE0
ms.date: 04/30/2018
keywords: ["IoSetActivityIdThread function"]
ms.keywords: IoSetActivityIdThread, IoSetActivityIdThread routine [Kernel-Mode Driver Architecture], kernel.iosetactivityidthread, ntddk/IoSetActivityIdThread
f1_keywords:
 - "ntddk/IoSetActivityIdThread"
 - "IoSetActivityIdThread"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows 8.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoSetActivityIdThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoSetActivityIdThread function


## -description


The IoSetActivityIdThread routine associates an activity ID with the current thread. Drivers should use this routine when they are tracing aware and are issuing I/O on a worker thread.


## -parameters




### -param ActivityId

The activity ID provided by caller.


## -returns



The activity ID that was previously set on the thread. Drivers must call IoClearActivityIdThread with this pointer when tracing is completed within the same thread context.




## -remarks



Drivers that use  I/O work items do not need to call this routine because the I/O subsystem takes care of propagating activity IDs to threads in that case.



