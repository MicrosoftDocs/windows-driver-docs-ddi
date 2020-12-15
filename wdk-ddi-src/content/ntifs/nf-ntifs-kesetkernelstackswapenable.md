---
UID: NF:ntifs.KeSetKernelStackSwapEnable
title: KeSetKernelStackSwapEnable function (ntifs.h)
description: The KeSetKernelStackSwapEnable routine enables and disables swapping of the caller's stack to disk.
old-location: kernel\kesetkernelstackswapenable.htm
tech.root: kernel
ms.date: 08/21/2020
keywords: ["KeSetKernelStackSwapEnable function"]
ms.keywords: KeSetKernelStackSwapEnable, KeSetKernelStackSwapEnable routine [Kernel-Mode Driver Architecture], k105_160eb1a2-1d12-4ca4-b83d-4bcb5636145e.xml, kernel.kesetkernelstackswapenable, ntifs/KeSetKernelStackSwapEnable
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeSetKernelStackSwapEnable
 - ntifs/KeSetKernelStackSwapEnable
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSetKernelStackSwapEnable
---

# KeSetKernelStackSwapEnable function


## -description

The **KeSetKernelStackSwapEnable** routine enables and disables swapping of the caller's stack to disk.

## -parameters

### -param Enable

[in] Specifies whether to enable swapping of the stack that belongs to the calling thread. If **TRUE**, swapping is enabled and the contents of the stack can be paged in and out of memory. If **FALSE**, swapping is disabled and the stack is memory-resident.

## -returns

**KeSetKernelStackSwapEnable** returns a BOOLEAN value that indicates whether stack swapping was enabled at the time that the call was initiated. This value is **TRUE** if stack swapping was previously enabled and is **FALSE** if it was disabled.

## -remarks

A kernel-mode driver can call this routine to control whether its stack is pageable or locked in memory.

Stack swapping can occur only if the thread is in a wait state that was caused by a request from a user-mode application. Stack swapping never occurs for wait states that are initiated by kernel-mode components, regardless of whether stack swapping is enabled.

It is not typically necessary to disable stack swapping. Do this only in  rare cases. For an example that discusses alternatives to disabling stack swapping, see the Example section below.

In a call to a kernel-mode wait routine, such as [**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md), the caller specifies a *WaitMode* parameter to indicate whether the caller waits in kernel mode or user mode. If *WaitMode* = **UserMode**, and if the wait duration is sufficiently long, the memory manager might page out sections of the stack that belongs to the waiting thread. However, if the stack contains data items that must remain memory-resident for the duration of the wait, the thread can prevent the stack from being paged out by calling **KeSetKernelStackSwapEnable** and specifying *Enable* = **FALSE**.

A thread must not exit (terminate) while stack swapping is disabled or a system bug check will occur.

### Example

In the following code example, a driver thread allocates an event on its stack and calls **KeSetKernelStackSwap** to temporarily lock the stack in memory until the event is signaled. The driver calls [**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md) with a **WaitReason** of **UserRequest** to indicate that its thread is in a wait state caused by a request from a user-mode application, and **WaitMode** set to **KernelMode** to indicate the wait is occurring in kernel mode. After the wait completes, the thread calls **KeSetKernelStackSwap** again, if necessary, to restore the original stack-swapping state of the thread.

``` cpp
KEVENT event;
BOOLEAN oldSwapEnable;
NTSTATUS status;

oldSwapEnable = KeSetKernelStackSwapEnable(FALSE);

KeInitializeEvent(&event, SynchronizationEvent, FALSE);

//
// TO DO: Insert code here to pass the event to another thread
// that will set the event to the signaled state.
//
...

status = KeWaitForSingleObject(&event, UserRequest, KernelMode, FALSE, NULL);

if (oldSwapEnable)
{
    KeSetKernelStackSwapEnable(TRUE);
}
```

An event object must be memory-resident while it can be set to a signaled or nonsignaled state, or while a thread waits on the event. For more information, see [Defining and Using an Event Object](/windows-hardware/drivers/kernel/defining-and-using-an-event-object).

Frequently, the use of the **KeSetKernelStackSwap** routine is unnecessary and can be avoided by allocating only pageable data items on the stack. In the previous example, the driver thread must lock the stack because the event object is allocated on the stack. A better alternative might be to simply allocate the event from nonpaged pool.

## -see-also

[**KeInitializeEvent**](../wdm/nf-wdm-keinitializeevent.md)

[**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md)
