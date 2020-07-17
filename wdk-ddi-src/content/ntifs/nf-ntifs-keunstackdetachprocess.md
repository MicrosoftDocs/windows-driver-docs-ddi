---
UID: NF:ntifs.KeUnstackDetachProcess
title: KeUnstackDetachProcess function (ntifs.h)
description: The KeUnstackDetachProcess routine detaches the current thread from the address space of a process and restores the previous attach state.
old-location: ifsk\keunstackdetachprocess.htm
tech.root: ifsk
ms.assetid: 3dd5b8f7-d8f8-4c02-80d1-76d0dbe06cd3
ms.date: 04/16/2018
keywords: ["KeUnstackDetachProcess function"]
ms.keywords: KeUnstackDetachProcess, KeUnstackDetachProcess routine [Installable File System Drivers], ifsk.keunstackdetachprocess, keref_47d45f58-d264-4633-8808-2172646df566.xml, ntifs/KeUnstackDetachProcess
f1_keywords:
 - "ntifs/KeUnstackDetachProcess"
 - "KeUnstackDetachProcess"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: < DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeUnstackDetachProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeUnstackDetachProcess function


## -description


The <b>KeUnstackDetachProcess</b> routine detaches the current thread from the address space of a process and restores the previous attach state. 
<div class="alert"><b>Caution</b>  Use this routine with extreme caution. (See the following Remarks section.)</div><div> </div>

## -parameters




### -param ApcState [in]

Opaque pointer to a KAPC_STATE structure that was returned from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kestackattachprocess">KeStackAttachProcess</a>. 


## -remarks



Every successful call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kestackattachprocess">KeStackAttachProcess</a> must be matched by a subsequent call to <b>KeUnstackDetachProcess</b>. 


<div class="alert"><b>Note</b>  Attaching a thread to a different process can prevent asynchronous I/O operations from completing and can potentially cause deadlocks. In general, the lines of code between the call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kestackattachprocess">KeStackAttachProcess</a>
      and the call to 
     <b>KeUnstackDetachProcess</b>
      should be very simple and should not call complex routines or send IRPs to other drivers.</div>
<div> </div>


For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcurrentprocess">IoGetCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetrequestorprocess">IoGetRequestorProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iothreadtoprocess">IoThreadToProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentirql">KeGetCurrentIrql</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentthread">KeGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kestackattachprocess">KeStackAttachProcess</a>



[PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>
 

 

