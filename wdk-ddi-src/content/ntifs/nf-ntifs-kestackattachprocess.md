---
UID: NF:ntifs.KeStackAttachProcess
title: KeStackAttachProcess function
author: windows-driver-content
description: The KeStackAttachProcess routine attaches the current thread to the address space of the target process.
old-location: ifsk\kestackattachprocess.htm
old-project: ifsk
ms.assetid: 52ac1410-8f8f-405a-9c81-a534c3cfbf51
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeStackAttachProcess, KeStackAttachProcess routine [Installable File System Drivers], ifsk.kestackattachprocess, keref_de4fc228-753f-4077-8372-e5330c96d317.xml, ntifs/KeStackAttachProcess
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
-	KeStackAttachProcess
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# KeStackAttachProcess function


## -description


The <b>KeStackAttachProcess</b> routine attaches the current thread to the address space of the target process.
<div class="alert"><b>Caution</b>  Use this routine with extreme caution. (See the note in the Remarks section.)</div><div> </div>

## -syntax


````
VOID KeStackAttachProcess(
  _Inout_ PRKPROCESS   Process,
  _Out_   PRKAPC_STATE ApcState
);
````


## -parameters




### -param PROCESS

TBD


### -param ApcState [out]

An opaque pointer to a KAPC_STATE structure. The caller must allocate storage for this structure either from nonpaged pool or from the caller's own thread stack. 


#### - Process [in, out]

Pointer to the target process object. This parameter can be a PEPROCESS pointer returned by <a href="..\wdm\nf-wdm-iogetcurrentprocess.md">IoGetCurrentProcess</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>. 


## -returns



None




## -remarks



<b>KeStackAttachProcess</b> attaches the current thread to the address space of the process pointed to by the <i>Process</i> parameter. If the current thread was already attached to another process, the <i>ApcState</i> parameter receives the current APC state before <b>KeStackAttachProcess</b> attaches to the new process. 

Every call to <b>KeStackAttachProcess</b> must be matched by a subsequent call to <a href="..\ntifs\nf-ntifs-keunstackdetachprocess.md">KeUnstackDetachProcess</a>. 


<div class="alert"><b>Note</b>  
     Attaching a thread to a different process can prevent asynchronous I/O operations from completing and can potentially cause deadlocks. In general, the lines of code between the call to 
     <b>KeStackAttachProcess</b>
      and the call to 
     <a href="..\ntifs\nf-ntifs-keunstackdetachprocess.md">KeUnstackDetachProcess</a>
      should be very simple and should not call complex routines or send IRPs to other drivers. 
    </div>
<div> </div>


For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>. 




## -see-also

<a href="..\wdm\nf-wdm-kegetcurrentthread.md">KeGetCurrentThread</a>



<a href="..\ntifs\nf-ntifs-keunstackdetachprocess.md">KeUnstackDetachProcess</a>



<a href="..\wdm\nf-wdm-iogetcurrentprocess.md">IoGetCurrentProcess</a>



<a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a>



<a href="..\ntifs\nf-ntifs-iogetrequestorprocess.md">IoGetRequestorProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>



<a href="..\ntifs\nf-ntifs-iothreadtoprocess.md">IoThreadToProcess</a>



<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeStackAttachProcess routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

