---
UID: NC:wdm.DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE
tech.root: kernel
title: DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE
ms.date: 09/09/2025
targetos: Windows
description: Defines a callback routine that runs in a hot-swappable worker thread.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE
f1_keywords:
 - DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE
 - wdm/DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE
dev_langs:
 - c++
helpviewer_keywords:
 - DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE
ai-usage: ai-assisted
---

## -description

The **DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE** callback defines a routine that runs in a hot-swappable worker thread created by [**IoDriverProxyCreateHotSwappableWorkerThread**](nf-wdm-iodriverproxycreatehotswappableworkerthread.md).

## -parameters

### -param WorkerContext

[in] A pointer to driver-defined context information that was specified when the worker thread was created. This context is passed through from the **Context** field of the [**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT**](ns-wdm-driver_proxy_hotswap_worker_routine_start_context.md) structure.

### -param WaitStatus

[in] The status returned from the wait operation. This indicates why the worker thread was awakened. See [**KeWaitForMultipleObjects**](nf-wdm-kewaitformultipleobjects.md) for possible wait status values.

## -returns

**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE** returns one of the following values:

| Return value | Description |
|--------------|-------------|
| TRUE | The worker thread should continue running and wait again on the specified objects. |
| FALSE | The worker thread should terminate. |

## -remarks

This callback is invoked when the worker thread wakes up from waiting on kernel objects. The routine determines whether the thread should continue running or terminate.

This callback routine runs at PASSIVE_LEVEL in the context of a system worker thread created specifically for hot-swappable operations. The thread maintains the same IRQL throughout its execution (_IRQL_requires_same_).

The worker routine is called each time the thread wakes up from waiting on the kernel objects specified in the [**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT**](ns-wdm-driver_proxy_hotswap_worker_routine_start_context.md) structure. Based on the **WaitStatus** and the current state of the driver, the routine should decide whether to continue processing (return TRUE) or terminate the worker thread (return FALSE).

The worker thread infrastructure ensures that the thread can be safely terminated and recreated as part of driver hot-swap operations, maintaining system stability during runtime driver updates.

## -see-also

[**IoDriverProxyCreateHotSwappableWorkerThread**](nf-wdm-iodriverproxycreatehotswappableworkerthread.md)

[**DRIVER_PROXY_HOTSWAP_WORKER_ROUTINE_START_CONTEXT**](ns-wdm-driver_proxy_hotswap_worker_routine_start_context.md)
