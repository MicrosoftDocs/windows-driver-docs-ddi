---
UID: NS:wdm._DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
tech.root: kernel
title: DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
ms.date: 09/11/2025
targetos: Windows
description: Contains parameters for starting a hot-swappable worker thread.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.typenames: DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT, *PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
f1_keywords:
 - _DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - wdm/_DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - wdm/PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
 - wdm/DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
ai-usage: ai-assisted
---

## -description

The **DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT** structure contains the parameters needed to start a hot-swappable worker thread using [**IoDriverProxyCreateHotSwappableWorkerThread**](nf-wdm-iodriverproxycreatehotswappableworkerthread.md).

## -struct-fields

### -field WorkerRoutine

A pointer to a [**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE**](nc-wdm-driver_proxy_hotswap_worker_routine.md) callback function that will be called when the worker thread wakes up from waiting on the specified events.

### -field Context

A pointer to driver-defined context information that will be passed to the **WorkerRoutine** callback. This allows the driver to provide additional data needed by the worker routine.

### -field WaitType

The type of wait operation to perform. Specify either **WaitAll**, indicating that all of the specified objects must attain a signaled state before the wait is satisfied; or **WaitAny**, indicating that any one of the objects must attain a signaled state before the wait is satisfied.

### -field WaitReason

The reason for the wait. Drivers should set this value to **Executive** or, if the driver is doing work on behalf of a user and is running in the context of a user thread, to **UserRequest**.

### -field WaitMode

Whether the caller waits in **KernelMode** or **UserMode**. Intermediate and lowest-level drivers should specify **KernelMode**. If the set of objects waited on includes a mutex, the caller must specify **KernelMode**.

### -field Altertable

A Boolean value that indicates whether the thread can be alerted while it is in the waiting state.

### -field HasTimeout

A Boolean value that indicates whether a timeout value is specified. If TRUE, the **Timeout** field contains a valid timeout value. If FALSE, the wait operation will wait indefinitely.

### -field Timeout

A pointer to a time-out value that specifies the absolute or relative time, in 100-nanosecond units, at which the wait is to be completed.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

If *Timeout = 0, the routine returns without waiting. If the caller supplies a NULL pointer, the routine waits indefinitely until any or all of the dispatcher objects are set to the signaled state.

### -field EventCount

The number of events in the **Events** array. This value determines how many kernel objects the worker thread will wait on.

### -field Events[ANYSIZE_ARRAY]

An array of pointers to **KEVENT** objects that the worker thread will wait on. The array size is determined by the **EventCount** field. The worker thread will wait for these events according to the **WaitType** specification.

## -remarks

This structure configures how the worker thread will wait for kernel objects and defines the callback routine that will be invoked when the wait completes.

This structure is used to configure a hot-swappable worker thread that can be safely terminated and recreated during driver hot-swap operations. The structure provides all the necessary parameters for the underlying kernel wait operations.

The worker thread created with this structure will repeatedly wait on the specified events and call the **WorkerRoutine** callback each time the wait completes. The callback can then decide whether the thread should continue running or terminate.

The hot-swappable nature of the worker thread means it can be safely stopped and restarted as part of driver update operations, maintaining system stability during runtime driver replacements.

## -see-also

[**IoDriverProxyCreateHotSwappableWorkerThread**](nf-wdm-iodriverproxycreatehotswappableworkerthread.md)

[**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE**](nc-wdm-driver_proxy_hotswap_worker_routine.md)

[**KEVENT**](/windows-hardware/drivers/kernel/eprocess)
