---
UID: NF:ntifs.KeUnstackDetachProcess
title: KeUnstackDetachProcess function
author: windows-driver-content
description: The KeUnstackDetachProcess routine detaches the current thread from the address space of a process and restores the previous attach state.
old-location: ifsk\keunstackdetachprocess.htm
old-project: ifsk
ms.assetid: 3dd5b8f7-d8f8-4c02-80d1-76d0dbe06cd3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeUnstackDetachProcess, KeUnstackDetachProcess routine [Installable File System Drivers], ifsk.keunstackdetachprocess, keref_47d45f58-d264-4633-8808-2172646df566.xml, ntifs/KeUnstackDetachProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeUnstackDetachProcess
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeUnstackDetachProcess function


## -description


The <b>KeUnstackDetachProcess</b> routine detaches the current thread from the address space of a process and restores the previous attach state. 
<div class="alert"><b>Caution</b>  Use this routine with extreme caution. (See the following Remarks section.)</div><div> </div>

## -syntax


````
VOID KeUnstackDetachProcess(
  _In_ PRKAPC_STATE ApcState
);
````


## -parameters




### -param ApcState [in]

Opaque pointer to a KAPC_STATE structure that was returned from a previous call to <a href="..\ntifs\nf-ntifs-kestackattachprocess.md">KeStackAttachProcess</a>. 


## -returns



None




## -remarks



Every successful call to <a href="..\ntifs\nf-ntifs-kestackattachprocess.md">KeStackAttachProcess</a> must be matched by a subsequent call to <b>KeUnstackDetachProcess</b>. 


<div class="alert"><b>Note</b>  Attaching a thread to a different process can prevent asynchronous I/O operations from completing and can potentially cause deadlocks. In general, the lines of code between the call to 
     <a href="..\ntifs\nf-ntifs-kestackattachprocess.md">KeStackAttachProcess</a>
      and the call to 
     <b>KeUnstackDetachProcess</b>
      should be very simple and should not call complex routines or send IRPs to other drivers.</div>
<div> </div>


For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>



<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\ntifs\nf-ntifs-iogetrequestorprocess.md">IoGetRequestorProcess</a>



<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>



<a href="..\ntifs\nf-ntifs-iothreadtoprocess.md">IoThreadToProcess</a>



<a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a>



<a href="..\wdm\nf-wdm-iogetcurrentprocess.md">IoGetCurrentProcess</a>



<a href="..\ntifs\nf-ntifs-kestackattachprocess.md">KeStackAttachProcess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeUnstackDetachProcess routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

