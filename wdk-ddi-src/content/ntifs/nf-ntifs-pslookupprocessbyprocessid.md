---
UID: NF:ntifs.PsLookupProcessByProcessId
title: PsLookupProcessByProcessId function (ntifs.h)
description: The PsLookupProcessByProcessId routine accepts the process ID of a process and returns a referenced pointer to EPROCESS structure of the process.
old-location: ifsk\pslookupprocessbyprocessid.htm
tech.root: ifsk
ms.assetid: f9c4bcab-5584-4b26-b4ff-6067d7ef1890
ms.date: 04/16/2018
keywords: ["PsLookupProcessByProcessId function"]
ms.keywords: PsLookupProcessByProcessId, PsLookupProcessByProcessId routine [Installable File System Drivers], ifsk.pslookupprocessbyprocessid, ntifs/PsLookupProcessByProcessId, psref_809b3ca8-eb8a-4ee0-9d74-b33b10664834.xml
f1_keywords:
 - "ntifs/PsLookupProcessByProcessId"
 - "PsLookupProcessByProcessId"
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
- PsLookupProcessByProcessId
targetos: Windows
req.typenames: 
---

# PsLookupProcessByProcessId function


## -description


The <b>PsLookupProcessByProcessId</b> routine accepts the process ID of a process and returns a referenced pointer to EPROCESS structure of the process.


## -parameters




### -param ProcessId 
[in]
Specifies the process ID of the process.


### -param Process 
[out]
Returns a referenced pointer to the EPROCESS structure of process specified by <i>ProcessId</i>.


## -returns



<b>PsLookupProcessByProcessId </b>returns STATUS_SUCCESS on success or an appropriate NTSTATUS value, such as: 

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
  
Specifies in Windows XP and earlier versions of Windows the process ID was not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_CID</b></dt>
</dl>
</td>
<td width="60%">

Specifies in Windows Vista and later versions of Windows the specified client ID is not valid.
  
</td>
</tr>


</table>
 




## -remarks



This routine is available on Windows 2000 and later versions. 

If the call to <b>PsLookupProcessByProcessId</b> is successful, <b>PsLookupProcessByProcessID</b> increases the reference count on the object returned in the <i>Process</i> parameter. Consequently, when a driver has completed using the <i>Process</i> parameter, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a> to dereference the <i>Process</i> parameter received from the <b>PsLookupProcessByProcessID</b> routine. 

The EPROCESS structure is an opaque data structure used internally by the operating system. This structure can be passed to other routines to access specific information in this structure.

A file system filter driver can enumerate active processes and then call <b>PsLookupProcessByProcessId</b> to convert a process ID to an EPROCESS structure. The process ID is available in the process create routine. A file system filter driver can set a process notification callback routine using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">PsSetCreateProcessNotifyRoutine</a>. In the notification callback routine, the file system filter driver can use the passed in <i>ProcessId</i> parameter and call <b>PsLookupProcessByProcessID </b>to locate the EPROCESS structure. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutine">PsSetCreateThreadNotifyRoutine</a> can also be used to set a notification routine that returns the process ID when a thread ID is created.

The <b>PsLookupProcessByProcessId</b> routine contains pageable code. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



[PsGetCurrentProcess](https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer#psgetcurrentprocess)



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentprocessid">PsGetCurrentProcessId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread">PsGetCurrentThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthreadid">PsGetCurrentThreadId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pslookupthreadbythreadid">PsLookupThreadByThreadId</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremovecreatethreadnotifyroutine">PsRemoveCreateThreadNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psremoveloadimagenotifyroutine">PsRemoveLoadImageNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutine">PsSetCreateProcessNotifyRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetloadimagenotifyroutine">PsSetLoadImageNotifyRoutine</a>
 

 

