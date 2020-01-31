---
UID: NF:ntifs.PsIsSystemThread
title: PsIsSystemThread function (ntifs.h)
description: The PsIsSystemThread routine checks whether a given thread is a system thread.
old-location: kernel\psissystemthread.htm
tech.root: kernel
ms.assetid: ecbea013-b876-4690-a455-ebe420a4f050
ms.date: 04/30/2018
ms.keywords: PsIsSystemThread, PsIsSystemThread routine [Kernel-Mode Driver Architecture], k108_eacaf1ad-4ab8-49a6-9d43-3aba7821e110.xml, kernel.psissystemthread, ntifs/PsIsSystemThread
f1_keywords:
 - "ntifs/PsIsSystemThread"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsIsSystemThread
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsIsSystemThread function


## -description


The <b>PsIsSystemThread</b> routine checks whether a given thread is a system thread.


## -parameters




### -param Thread [in]

Pointer to the thread to be checked. 


## -returns



<b>PsIsSystemThread</b> returns <b>TRUE</b> if the specified thread is a system thread, <b>FALSE</b> otherwise.




## -remarks



For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ioissystemthread">IoIsSystemThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>
 

 

