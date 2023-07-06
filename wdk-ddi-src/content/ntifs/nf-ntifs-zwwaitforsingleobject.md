---
UID: NF:ntifs.ZwWaitForSingleObject
title: ZwWaitForSingleObject function (ntifs.h)
description: Learn more about the ZwWaitForSingleObject routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["ZwWaitForSingleObject function"]
ms.keywords: NtWaitForSingleObject, ZwWaitForSingleObject, ZwWaitForSingleObject routine [Kernel-Mode Driver Architecture], k111_44a7540a-fbf5-4f2e-92d1-0d23cc41a081.xml, kernel.zwwaitforsingleobject, ntifs/NtWaitForSingleObject, ntifs/ZwWaitForSingleObject
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait
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
 - ZwWaitForSingleObject
 - ntifs/ZwWaitForSingleObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwWaitForSingleObject
---

# ZwWaitForSingleObject function

## -description

The **ZwWaitForSingleObject** routine waits until the specified object attains a state of Signaled. An optional time-out can also be specified.

## -parameters

### -param Handle [in]

A handle to the object.

### -param Alertable [in]

A boolean value that specifies whether the wait is alertable.

### -param Timeout [in, optional]

An optional pointer to a time-out value that specifies the absolute or relative time at which the wait is to be completed. A negative value specifies an interval relative to the current time. The value should be expressed in units of 100 nanoseconds. Absolute expiration times track any changes in the system time. Relative expiration times are not affected by system time changes.

## -returns

**ZwWaitForSingleObject** can return one of the following possible status codes:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED  | The caller didn't have the required privileges to the event specified by the **Handle** parameter. |
| STATUS_ALERTED        | The wait was aborted to deliver an alert to the current thread. |
| STATUS_INVALID_HANDLE | The supplied **Handle** parameter was invalid. |
| STATUS_SUCCESS        | The specified object satisfied the wait. |
| STATUS_TIMEOUT        | A time-out occurred before the object was set to a signaled state. This value can be returned when the specified set of wait conditions cannot be immediately met and the **Timeout** parameter is set to zero. |
| STATUS_USER_APC       | The wait was aborted to deliver a user APC to the current thread. |

Note that the NT_SUCCESS macro recognizes the STATUS_ALERTED, STATUS_SUCCESS, STATUS_TIMEOUT, and STATUS_USER_APC status values as "success" values.

## -remarks

**ZwWaitForSingleObject** waits until the specified object attains a state of Signaled. An optional timeout can also be specified. **ZwWaitForSingleObject** examines the current state of the specified object to determine whether the wait can be satisfied immediately. If so, actions are performed. Otherwise, the current thread is put in a waiting state and a new thread is selected for execution on the current processor.

If a **Timeout** parameter is not specified, then the wait will not be satisfied until the object attains a state of Signaled. If a **Timeout** parameter is specified, and the object has not attained a state of Signaled when the time-out expires, then the wait is automatically satisfied. If an explicit **Timeout** value of zero is specified, then no wait will occur if the wait cannot be satisfied immediately. A **Timeout** value of zero allows the testing of a set of wait conditions and for the conditional performance of any side effects if the wait can be immediately satisfied, as in the acquisition of a mutex. The wait can also be specified as alertable.

The **Alertable** parameter specifies whether the thread can be alerted and its wait state consequently aborted. If the value of this parameter is FALSE then the thread cannot be alerted. The only exception to this rule is that of a terminating thread. Under certain circumstances a terminating thread can be alerted while it is in the process of winding down. A thread is automatically made alertable, for instance, when terminated by a user with a CTRL+C.

If the value of **Alertable**is TRUE and one of the following conditions is present, the thread will be alerted:

* If the origin of the alert is an internal, undocumented kernel-mode routine used to alert threads.
* The origin of the alert is a user-mode APC.

In the first of these two cases, the thread's wait is satisfied with a completion status of STATUS_ALERTED. In the second case, it is satisfied with a completion status of STATUS_USER_APC.

The thread must be alertable for a user-mode APC to be delivered. This is not the case for kernel-mode APCs. A kernel-mode APC can be delivered and executed even though the thread is not alerted. Once the APC's execution completes, the thread's wait resumes. A thread is never alerted, nor is its wait aborted, by the delivery of a kernel-mode APC.

The delivery of kernel-mode APCs to a waiting thread does not depend on whether the thread can be alerted. If the kernel-mode APC is a special kernel-mode APC, then the APC is delivered provided that the IRQL is less than APC_LEVEL. If the kernel-mode APC is a normal kernel-mode APC, then the APC is delivered provided that the following three conditions hold: (1) the IRQL is less than APC_LEVEL, (2) no kernel APC is in progress, and (3) the thread is not in a critical section.

If the handle passed to **ZwWaitForSingleObject** refers to a mutex, the APC delivery is the same as for all other dispatcher objects during the wait. However, once **ZwWaitForSingleObject** returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

It is especially important to check the return value of **ZwWaitForSingleObject** when the **Alertable** parameter is TRUE, because **ZwWaitForSingleObject** might return early with a status of STATUS_USER_APC or STATUS_ALERTED.

All long term waits can be aborted by a user if the **Alertable** parameter is set to FALSE.

For additional information, see [Do Waiting Threads Receive Alerts and APCs?](/windows-hardware/drivers/kernel/waits-and-apcs)

Callers of **ZwWaitForSingleObject** must be running at IRQL less than or equal to DISPATCH_LEVEL. Usually, the caller must be running at IRQL PASSIVE_LEVEL and in a nonarbitrary thread context. A call while running at IRQL DISPATCH_LEVEL is valid if and only if the caller specifies a **Timeout** parameter of zero. That is, a driver must not wait for a nonzero interval at IRQL equal to DISPATCH_LEVEL.

Time-out intervals are measured relative to the system clock, and the accuracy of the time-out measurement is limited by the granularity of the system clock. For more information, see [Timer Accuracy](/windows-hardware/drivers/kernel/timer-accuracy).

If the call to the **ZwWaitForSingleObject** function occurs in user mode, you should use the name "**NtWaitForSingleObject**" instead of "**ZwWaitForSingleObject**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**IoCreateNotificationEvent**](../wdm/nf-wdm-iocreatenotificationevent.md)

[**IoCreateSynchronizationEvent**](../wdm/nf-wdm-iocreatesynchronizationevent.md)

[**KeClearEvent**](../wdm/nf-wdm-keclearevent.md)

[**KeResetEvent**](../wdm/nf-wdm-keresetevent.md)

[**KeSetEvent**](../wdm/nf-wdm-kesetevent.md)

[**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md)

[**ZwClose**](nf-ntifs-ntclose.md)

[**ZwCreateEvent**](nf-ntifs-zwcreateevent.md)

[**ZwSetEvent**](nf-ntifs-zwsetevent.md)
