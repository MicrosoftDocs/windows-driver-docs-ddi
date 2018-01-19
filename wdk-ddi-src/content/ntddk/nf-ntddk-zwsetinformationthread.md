---
UID: NF:ntddk.ZwSetInformationThread
title: ZwSetInformationThread function
author: windows-driver-content
description: The ZwSetInformationThread routine sets the priority of a thread.
old-location: kernel\zwsetinformationthread.htm
old-project: kernel
ms.assetid: ec67c643-bc91-4784-b5f4-09a20e8406c3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwSetInformationThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwSetInformationThread,NtSetInformationThread
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# ZwSetInformationThread function



## -description
The <b>ZwSetInformationThread</b> routine sets the priority of a thread.



## -syntax

````
NTSTATUS ZwSetInformationThread(
  _In_ HANDLE          ThreadHandle,
  _In_ THREADINFOCLASS ThreadInformationClass,
  _In_ PVOID           ThreadInformation,
  _In_ ULONG           ThreadInformationLength
);
````


## -parameters

### -param ThreadHandle [in]

Handle to the thread object. To create a new thread and get a handle to it, call <a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>. To specify the current thread, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566434">ZwCurrentThread</a> macro.


### -param ThreadInformationClass [in]

One of the system-defined values in the THREADINFOCLASS enumeration (see ntddk.h), <b>ThreadPriority</b>,   <b>ThreadBasePriority</b>,  <b>ThreadPagePriority</b>, or <b>ThreadPowerThrottlingState</b>.


### -param ThreadInformation [in]

Pointer to a variable that specifies the information to set. 

If <b>ThreadInformationClass</b> is <b>ThreadPriority</b>, this value must be &gt; LOW_PRIORITY and &lt;= HIGH_PRIORITY. 

If <b>ThreadInformationClass</b> is <b>ThreadBasePriority</b>, this value must fall within the system's valid base-priority range and the original priority class for the given thread. That is, if a thread's priority class is variable, that thread's base priority cannot be reset to a real-time priority value, and vice versa.

If <b>ThreadInformationClass</b> is <b>ThreadPagePriority</b>, this value is a pointer to a <b>PAGE_PRIORITY_INFORMATION</b> structure, see ntddk.h. The <b>PagePriority</b> member value must be one of these values. 

If <b>ThreadInformationClass</b> is <b>ThreadPowerThrottlingState</b>, this value is a pointer to a <a href="https://msdn.microsoft.com/85659694-f93a-42dc-9fa4-f6fea6ad71d0">POWER_THROTTLING_THREAD_STATE</a> structure, see ntddk.h. The <b>PagePriority</b> member value must be one of these values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param MEMORY_PRIORITY_VERY_LOW
### -param 1

</td>
<td width="60%">
Very low memory priority.

</td>
</tr>
<tr>

### -param MEMORY_PRIORITY_LOW
### -param 2

</td>
<td width="60%">
Low memory priority.

</td>
</tr>
<tr>

### -param MEMORY_PRIORITY_MEDIUM
### -param 3

</td>
<td width="60%">
Medium memory priority.

</td>
</tr>
<tr>

### -param MEMORY_PRIORITY_BELOW_NORMAL
### -param 4

</td>
<td width="60%">
Below normal memory priority.

</td>
</tr>
<tr>

### -param MEMORY_PRIORITY_NORMAL
### -param 5

</td>
<td width="60%">
Normal memory priority. This is the default priority for all threads and processes on the system.

</td>
</tr>
</table>
 


### -param ThreadInformationLength [in]

The size, in bytes, of <b>ThreadInformation</b>. 


## -returns
<b>ZwSetInformationThread</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. Possible error codes include STATUS_INFO_LENGTH_MISMATCH or STATUS_INVALID_PARAMETER.


## -remarks
<b>ZwSetInformationThread</b> can be called by higher-level drivers to set the priority of a thread for which they have a handle.

The caller must have THREAD_SET_INFORMATION access rights for the given thread in order to call this routine.

Usually, device and intermediate drivers that set up driver-created threads call <a href="..\ntddk\nf-ntddk-kesetbaseprioritythread.md">KeSetBasePriorityThread</a> or <a href="..\wdm\nf-wdm-kesetprioritythread.md">KeSetPriorityThread</a> from their driver-created threads, rather than calling <b>ZwSetInformationThread</b>. However, a driver can call <b>ZwSetInformationThread</b> to raise the priority of a driver-created thread before that thread runs.

Kernel mode drivers can call the <b>ZwSetInformationThread</b> function with <b>ThreadPagePriority</b> to specify a thread's page priority.

To help improve system performance, drivers should use the  function with <b>ThreadPagePriority</b> to lower the page priority of threads that perform background operations or access files and data that are not expected to be accessed again soon. For example, an anti-malware application might lower the priority of threads involved in scanning files.

To determine the page priority for a thread, call <a href="https://msdn.microsoft.com/0B3F4CCF-D727-46AD-B3E0-3217DA1F3486">ZwQueryInformationThread</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-kesetbaseprioritythread.md">KeSetBasePriorityThread</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesetprioritythread.md">KeSetPriorityThread</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pscreatesystemthread.md">PsCreateSystemThread</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetInformationThread routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

