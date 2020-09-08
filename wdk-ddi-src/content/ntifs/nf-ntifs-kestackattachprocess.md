---
UID: NF:ntifs.KeStackAttachProcess
title: KeStackAttachProcess function (ntifs.h)
description: The KeStackAttachProcess routine attaches the current thread to the address space of the target process.
old-location: ifsk\kestackattachprocess.htm
tech.root: ifsk
ms.assetid: 52ac1410-8f8f-405a-9c81-a534c3cfbf51
ms.date: 04/16/2018
keywords: ["KeStackAttachProcess function"]
ms.keywords: KeStackAttachProcess, KeStackAttachProcess routine [Installable File System Drivers], ifsk.kestackattachprocess, keref_de4fc228-753f-4077-8372-e5330c96d317.xml, ntifs/KeStackAttachProcess
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KeStackAttachProcess
 - ntifs/KeStackAttachProcess
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeStackAttachProcess
---

# KeStackAttachProcess function


## -description

The <b>KeStackAttachProcess</b> routine attaches the current thread to the address space of the target process.
<div class="alert"><b>Caution</b>  Use this routine with extreme caution. (See the note in the Remarks section.)</div><div> </div>

## -parameters

### -param PROCESS

Pointer to the target process object. This parameter can be a PEPROCESS pointer returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcurrentprocess">IoGetCurrentProcess</a> or [PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess).

### -param ApcState 

[out]
An opaque pointer to a KAPC_STATE structure. The caller must allocate storage for this structure either from nonpaged pool or from the caller's own thread stack.

## -remarks

<b>KeStackAttachProcess</b> attaches the current thread to the address space of the process pointed to by the <i>Process</i> parameter. If the current thread was already attached to another process, the <i>ApcState</i> parameter receives the current APC state before <b>KeStackAttachProcess</b> attaches to the new process. 

Every call to <b>KeStackAttachProcess</b> must be matched by a subsequent call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keunstackdetachprocess">KeUnstackDetachProcess</a>. 


<div class="alert"><b>Note</b>  
     Attaching a thread to a different process can prevent asynchronous I/O operations from completing and can potentially cause deadlocks. In general, the lines of code between the call to 
     <b>KeStackAttachProcess</b>
      and the call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keunstackdetachprocess">KeUnstackDetachProcess</a>
      should be very simple and should not call complex routines or send IRPs to other drivers. 
    </div>
<div> </div>


For more information about using system threads and managing synchronization within a nonarbitrary thread context, see [Windows Kernel-Mode Process and Thread Manager](https://docs.microsoft.com/windows-hardware/drivers/kernel/windows-kernel-mode-process-and-thread-manager).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcurrentprocess">IoGetCurrentProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetrequestorprocess">IoGetRequestorProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iothreadtoprocess">IoThreadToProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentirql">KeGetCurrentIrql</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetcurrentthread">KeGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-keunstackdetachprocess">KeUnstackDetachProcess</a>



[PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>

