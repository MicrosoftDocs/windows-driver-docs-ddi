---
UID: NF:ntifs.IoWriteErrorLogEntry
title: IoWriteErrorLogEntry function
author: windows-driver-content
description: The IoWriteErrorLogEntry routine queues a given error log packet to the system error logging thread.
old-location: kernel\iowriteerrorlogentry.htm
old-project: kernel
ms.assetid: 1259c344-584c-410a-a152-5de1f433082c
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoWriteErrorLogEntry, IoWriteErrorLogEntry routine [Kernel-Mode Driver Architecture], k104_1822a499-059a-41c8-b97b-aa3a5bfd22e3.xml, kernel.iowriteerrorlogentry, wdm/IoWriteErrorLogEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoWriteErrorLogEntry
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# IoWriteErrorLogEntry function


## -description


The <b>IoWriteErrorLogEntry</b> routine queues a given error log packet to the system error logging thread.


## -parameters




### -param ElEntry [in]

Pointer to the error log packet the driver has allocated with <a href="https://msdn.microsoft.com/library/windows/hardware/ff548245">IoAllocateErrorLogEntry</a> and filled in by the caller. 


## -returns



None




## -remarks



<b>IoWriteErrorLogEntry</b> frees the error log entry. Drivers must not call <b>IoFreeErrorLogEntry</b> on a log entry that they have already passed to <b>IoWriteErrorLogEntry</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550571">IO_ERROR_LOG_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548245">IoAllocateErrorLogEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549107">IoFreeErrorLogEntry</a>
 

 

