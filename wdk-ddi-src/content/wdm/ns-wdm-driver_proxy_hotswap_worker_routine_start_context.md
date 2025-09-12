---
UID: NS:wdm._DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
tech.root: kernel
title: DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT
ms.date: 09/09/2025
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

```cpp
typedef struct _DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT {
    PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE WorkerRoutine;
    PVOID Context;
    WAIT_TYPE WaitType;
    KWAIT_REASON WaitReason;
    KPROCESSOR_MODE WaitMode;
    BOOLEAN Altertable;
    BOOLEAN HasTimeout;
    LARGE_INTEGER Timeout;
    ULONG EventCount;
    PKEVENT Events[ANYSIZE_ARRAY];
} DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT, *PDRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT;
```

This structure configures how the worker thread will wait for kernel objects and defines the callback routine that will be invoked when the wait completes.

## -struct-fields

### -field WorkerRoutine

A pointer to a [**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE**](nc-wdm-driver_proxy_hotswap_worker_routine.md) callback function that will be called when the worker thread wakes up from waiting on the specified events.

### -field Context

A pointer to driver-defined context information that will be passed to the **WorkerRoutine** callback. This allows the driver to provide additional data needed by the worker routine.

### -field WaitType

Specifies the type of wait operation to perform. This is a **WAIT_TYPE** enumeration value:

- **WaitAll** - Wait for all specified events to be signaled
- **WaitAny** - Wait for any of the specified events to be signaled

### -field WaitReason

Specifies the reason for the wait operation. This is a **KWAIT_REASON** enumeration value that indicates the purpose of the wait, such as **Executive**, **UserRequest**, or other system-defined reasons.

### -field WaitMode

Specifies the processor mode for the wait operation. This is a **KPROCESSOR_MODE** enumeration value:

- **KernelMode** - Wait in kernel mode
- **UserMode** - Wait in user mode

### -field Altertable

A Boolean value that specifies whether the wait is alertable. If **TRUE**, the wait can be interrupted by APCs (Asynchronous Procedure Calls). If **FALSE**, the wait is not alertable.

### -field HasTimeout

A Boolean value that indicates whether a timeout value is specified. If **TRUE**, the **Timeout** field contains a valid timeout value. If **FALSE**, the wait operation will wait indefinitely.

### -field Timeout

A **LARGE_INTEGER** value that specifies the timeout for the wait operation, in 100-nanosecond intervals. This field is only used if **HasTimeout** is **TRUE**. A negative value indicates a relative timeout, while a positive value indicates an absolute timeout.

### -field EventCount

The number of events in the **Events** array. This value determines how many kernel objects the worker thread will wait on.

### -field Events[ANYSIZE_ARRAY]

An array of pointers to **KEVENT** objects that the worker thread will wait on. The array size is determined by the **EventCount** field. The worker thread will wait for these events according to the **WaitType** specification.

## -remarks

This structure is used to configure a hot-swappable worker thread that can be safely terminated and recreated during driver hot-swap operations. The structure provides all the necessary parameters for the underlying kernel wait operations.

The worker thread created with this structure will repeatedly wait on the specified events and call the **WorkerRoutine** callback each time the wait completes. The callback can then decide whether the thread should continue running or terminate.

Key considerations when using this structure:

- All event objects in the **Events** array must remain valid for the lifetime of the worker thread
- The **Context** pointer should point to memory that remains valid throughout the thread's execution
- The **WorkerRoutine** callback runs at PASSIVE_LEVEL and can perform operations that require this IRQL
- The structure should be allocated from non-paged memory if it needs to persist across power state changes

The hot-swappable nature of the worker thread means it can be safely stopped and restarted as part of driver update operations, maintaining system stability during runtime driver replacements.

## -see-also

[**IoDriverProxyCreateHotSwappableWorkerThread**](nf-wdm-iodriverproxycreatehotswappableworkerthread.md)

[**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE**](nc-wdm-driver_proxy_hotswap_worker_routine.md)

[**KEVENT**](/windows-hardware/drivers/kernel/eprocess)

