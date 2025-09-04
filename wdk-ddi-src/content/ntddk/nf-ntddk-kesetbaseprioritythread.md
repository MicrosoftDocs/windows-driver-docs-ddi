---
UID: NF:ntddk.KeSetBasePriorityThread
title: KeSetBasePriorityThread function (ntddk.h)
description: The KeSetBasePriorityThread routine sets the run-time priority, relative to the current process, for a given thread.
tech.root: kernel
ms.date: 09/04/2025
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeSetBasePriorityThread
 - ntddk/KeSetBasePriorityThread
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSetBasePriorityThread
---

## -description

The **KeSetBasePriorityThread** routine sets the run-time priority, relative to the current process, for a given thread.

## -parameters

### -param Thread [in, out]

Pointer to a dispatcher object of type KTHREAD.

### -param Increment [in]

Specifies the value to be added to the base priority of the process for the **Thread**. This value can be positive or negative.

The effective range depends on the process's priority class:

- For variable priority class processes: The resulting priority must stay within 1 to (`LOW_REALTIME_PRIORITY` - 1)
- For real-time priority class processes: The resulting priority must stay within `LOW_REALTIME_PRIORITY` to `HIGH_PRIORITY`

If the absolute value of **Increment** is greater than or equal to `(HIGH_PRIORITY + 1) / 2`, priority saturation occurs, meaning subsequent changes to the parent process base priority will not affect this thread's base priority.

## -returns

**KeSetBasePriorityThread** returns the previous base priority increment of the given thread. The previous base priority increment is defined as the difference between the specified thread's old base priority and the base priority of the thread's process.

Special return values:

- This function returns 0 when an attempt is made to change the priority of an idle thread (threads in the initial kernel process). The function does not allow idle thread priorities to be changed.

- For saturated threads, this function returns `((HIGH_PRIORITY + 1) / 2) * saturation_value` rather than the simple priority difference, where saturation_value is +1 or -1 depending on whether the thread was saturated at high or low priority.

## -remarks

The new base priority is computed by adding the given **Increment**, which can be a negative value, to the base priority of the specified thread's process. The resultant value is stored as the base priority of the specified thread.

Drivers that set up device-dedicated threads with variable priority attributes can call this routine to set such a thread's priority relative to the system process in which the thread is created.

The new base priority is restricted to the priority class of the given thread's process. Therefore, the base priority is not allowed to cross over from a variable priority class to a real-time priority class or vice versa.

**KeSetBasePriorityThread** is a relatively expensive operation that should be used sparingly. Avoid frequent calls to this function, as repeated priority changes (such as once per minute) can significantly impact system performance and prevent the scheduler from operating efficiently. Use this function only when persistent priority changes are required, not for temporary adjustments or periodic updates.

## -see-also

[**KeGetCurrentThread**](nf-wdm-kegetcurrentthread.md)

[**KeQueryPriorityThread**](nf-wdm-kequeryprioritythread.md)

[**KeSetPriorityThread**](nf-wdm-kesetprioritythread.md)
