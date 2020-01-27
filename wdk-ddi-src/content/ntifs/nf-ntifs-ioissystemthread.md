---
UID: NF:ntifs.IoIsSystemThread
title: IoIsSystemThread function (ntifs.h)
description: The IoIsSystemThread routine checks whether a given thread is a system thread.
old-location: ifsk\ioissystemthread.htm
tech.root: ifsk
ms.assetid: 1f3dc15f-14b5-4797-83be-ba3a01a1551b
ms.date: 04/16/2018
ms.keywords: IoIsSystemThread, IoIsSystemThread routine [Installable File System Drivers], ifsk.ioissystemthread, ioref_3e14f3af-c985-43a4-bc57-927483597c79.xml, ntifs/IoIsSystemThread
f1_keywords:
 - "ntifs/IoIsSystemThread"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoIsSystemThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoIsSystemThread function


## -description


The <b>IoIsSystemThread</b> routine checks whether a given thread is a system thread. 


## -parameters




### -param Thread [in]

Pointer to the thread to be checked. 


## -returns



<b>IoIsSystemThread</b> returns <b>TRUE</b> if the specified thread is a system thread, otherwise <b>FALSE</b>. 




## -remarks



For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psissystemthread">PsIsSystemThread</a>
 

 

