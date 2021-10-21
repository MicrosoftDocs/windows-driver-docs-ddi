---
UID: NF:storport.StorPortCreateSystemThread
tech.root: storage
title: StorPortCreateSystemThread
ms.date: 05/13/2021
targetos: Windows
description: StorPortCreateSystemThread creates a system thread and supplies a pointer to a context for the thread.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortCreateSystemThread
f1_keywords:
 - StorPortCreateSystemThread
 - storport/StorPortCreateSystemThread
dev_langs:
 - c++
---

## -description

**StorPortCreateSystemThread** creates a system thread and supplies a pointer to a context for the thread.

## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport's hardware device extension.

### -param StartRoutine [in]

Pointer to the entry point for the newly created system thread. This parameter is a function pointer to a [**STOR_THREAD_START_ROUTINE**](nc-storport-stor_thread_start_routine.md) callback that receives a single argument, which is the **StartContext** parameter value.

### -param StartContext [in/optional]

Pointer to a single argument that is passed to the thread when it begins execution.

### -param Priority [in/optional]

Pointer to a [**STOR_THREAD_PRIORITY**](ne-storport-stor_thread_priority.md) enum value that specifies the thread priority.

### -param ThreadContext [out/optional]

Pointer to a variable that will receive the thread context.

## -returns

**StorPortCreateSystemThread** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | A system thread has been successfully created. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the provided parameters are invalid. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

Miniport drivers that create device-dedicated threads call **StorPortCreateSystemThread**, either when they initialize or when I/O requests begin to come in to the driver's *Dispatch* routines. For example, a driver might create such a thread when it receives an asynchronous device control request.

The thread continues to run until either the system is shut down or the thread terminates itself by calling [**StorPortTerminateSystemThread**](nf-storport-storportterminatesystemthread.md).

Thread priority can be changed by calling [**StorPortSetPriorityThread**](nf-storport-storportsetprioritythread.md). A miniport should specify a thread priority value that avoids run-time priority inversions. See [Device-dedicated Threads](/windows-hardware/drivers/kernel/device-dedicated-threads) for more information.

For a given adapter, the maximum system threads that a miniport can create is the maximum logical processor count in the system.

## -see-also

[**STOR_THREAD_PRIORITY**](ne-storport-stor_thread_priority.md)

[**STOR_THREAD_START_ROUTINE**](nc-storport-stor_thread_start_routine.md)

[**StorPortSetPriorityThread**](nf-storport-storportsetprioritythread.md)

[**StorPortTerminateSystemThread**](nf-storport-storportterminatesystemthread.md)
