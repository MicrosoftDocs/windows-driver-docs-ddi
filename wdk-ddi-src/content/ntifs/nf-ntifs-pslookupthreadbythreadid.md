---
UID: NF:ntifs.PsLookupThreadByThreadId
title: PsLookupThreadByThreadId function (ntifs.h)
description: The PsLookupThreadByThreadId routine accepts the thread ID of a thread and returns a referenced pointer to the ETHREAD structure of the thread.
old-location: ifsk\pslookupthreadbythreadid.htm
tech.root: ifsk
ms.assetid: 4b61f480-6432-48db-9211-68a7d823d698
ms.date: 04/16/2018
keywords: ["PsLookupThreadByThreadId function"]
ms.keywords: PsLookupThreadByThreadId, PsLookupThreadByThreadId routine [Installable File System Drivers], ifsk.pslookupthreadbythreadid, ntifs/PsLookupThreadByThreadId, psref_36f0c499-8370-4257-849c-dc8bad2720cc.xml
f1_keywords:
 - "ntifs/PsLookupThreadByThreadId"
 - "PsLookupThreadByThreadId"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsLookupThreadByThreadId
targetos: Windows
req.typenames: 
---

# PsLookupThreadByThreadId function


## -description


The <b>PsLookupThreadByThreadId</b> routine accepts the thread ID of a thread and returns a referenced pointer to the ETHREAD structure of the thread.


## -parameters




### -param ThreadId [in]

Specifies the thread ID of the thread.


### -param Thread [out]

Returns a referenced pointer to the ETHREAD structure of thread specified by the <i>ThreadId</i>.


## -returns



<b>PsLookupThreadByThreadId </b>returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The thread ID was not found.

</td>
</tr>
</table>
 




## -remarks



This routine is available on Windows 2000 and later versions. 

If the call to <b>PsLookupThreadByThreadId</b> is successful, <b>PsLookupThreadByThreadId</b> increases the reference count on the object returned in the <i>Thread</i> parameter. Consequently, when a driver has completed using the <i>Thread</i> parameter, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> to dereference the <i>Thread</i> parameter received from the <b>PsLookupThreadByThreadId</b> routine. 

The ETHREAD structure is an opaque data structure used internally by the operating system. This structure can be passed to other routines to access specific information in this structure.

A file system filter driver can enumerate active threads by calling <b>PsLookupThreadByThreadId</b> to convert a thread ID to an ETHREAD structure. The thread ID is available in the thread create routine. A file system filter driver can set a thread notification callback routine using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>. In the notification callback routine, the file system filter driver can use the passed in <i>ThreadId</i> parameter and call <b>PsLookupThreadByThreadId </b>to locate the ETHREAD structure.

The <b>PsLookupThreadByThreadId</b> routine contains pageable code. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



[PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentprocessid">PsGetCurrentProcessId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthreadid">PsGetCurrentThreadId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pslookupprocessbyprocessid">PsLookupProcessByProcessId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremovecreatethreadnotifyroutine">PsRemoveCreateThreadNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremoveloadimagenotifyroutine">PsRemoveLoadImageNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine">PsSetLoadImageNotifyRoutine</a>
 

 

