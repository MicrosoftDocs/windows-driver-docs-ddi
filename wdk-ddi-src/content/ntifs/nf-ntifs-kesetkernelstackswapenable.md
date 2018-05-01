---
UID: NF:ntifs.KeSetKernelStackSwapEnable
title: KeSetKernelStackSwapEnable function
author: windows-driver-content
description: The KeSetKernelStackSwapEnable routine enables and disables swapping of the caller's stack to disk.
old-location: kernel\kesetkernelstackswapenable.htm
old-project: kernel
ms.assetid: ec914f67-b2c2-4370-8685-770bca045034
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: KeSetKernelStackSwapEnable, KeSetKernelStackSwapEnable routine [Kernel-Mode Driver Architecture], k105_160eb1a2-1d12-4ca4-b83d-4bcb5636145e.xml, kernel.kesetkernelstackswapenable, ntifs/KeSetKernelStackSwapEnable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeSetKernelStackSwapEnable
product: Windows
targetos: Windows
req.typenames: 
---

# KeSetKernelStackSwapEnable function


## -description


The <b>KeSetKernelStackSwapEnable</b> routine enables and disables swapping of the caller's stack to disk. 


## -parameters




### -param Enable [in]

Specifies whether to enable swapping of the stack that belongs to the calling thread. If <b>TRUE</b>, swapping is enabled and the contents of the stack can be paged in and out of memory. If <b>FALSE</b>, swapping is disabled and the stack is memory-resident. 


## -returns



<b>KeSetKernelStackSwapEnable</b> returns a BOOLEAN value that indicates whether stack swapping was enabled at the time that the call was initiated. This value is <b>TRUE</b> if stack swapping was previously enabled and is <b>FALSE</b> if it was disabled. 




## -remarks



A kernel-mode driver can call this routine to control whether its stack is pageable or locked in memory.

Stack swapping can occur only if the thread is in a wait state that was caused by a request from a user-mode application. Stack swapping never occurs for wait states that are initiated by kernel-mode components, regardless of whether stack swapping is enabled.

It is not typically necessary to disable stack swapping. Do this only in  rare cases. For an example that discusses alternatives to disabling stack swapping, see the following Examples section.

In a call to a kernel-mode wait routine, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>, the caller specifies a <i>WaitMode</i> parameter to indicate whether the caller waits in kernel mode or user mode. If <i>WaitMode</i> = <b>UserMode</b>, and if the wait duration is sufficiently long, the memory manager might page out sections of the stack that belongs to the waiting thread. However, if the stack contains data items that must remain memory-resident for the duration of the wait, the thread can prevent the stack from being paged out by calling <b>KeSetKernelStackSwapEnable</b> and specifying <i>Enable</i> = <b>FALSE</b>.

A thread must not exit (terminate) while stack swapping is disabled or a system bug check will occur.


#### Examples

In the following code example, a driver thread allocates an event on its stack and calls <b>KeSetKernelStackSwap</b> to temporarily lock the stack in memory until the event is signaled. After the wait completes, the thread calls <b>KeSetKernelStackSwap</b> again, if necessary, to restore the original stack-swapping state of the thread.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>KEVENT event;
BOOLEAN oldSwapEnable;
NTSTATUS status;

oldSwapEnable = KeSetKernelStackSwapEnable(FALSE);

KeInitializeEvent(&amp;event, SynchronizationEvent, FALSE);

//
// TO DO: Insert code here to pass the event to another thread 
// that will set the event to the signaled state.
//
...

status = KeWaitForSingleObject(&amp;event, UserRequest, KernelMode, FALSE, NULL);

if (oldSwapEnable)
{
    KeSetKernelStackSwapEnable(TRUE);
}</pre>
</td>
</tr>
</table></span></div>
An event object must be memory-resident while it can be set to a signaled or nonsignaled state, or while a thread waits on the event. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543006">Defining and Using an Event Object</a>.

Frequently, the use of the <b>KeSetKernelStackSwap</b> routine is unnecessary and can be avoided by allocating only pageable data items on the stack. In the previous example, the driver thread must lock the stack because the event object is allocated on the stack. A better alternative might be to simply allocate the event from nonpaged pool.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552137">KeInitializeEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

