---
UID: NF:storport.StorPortSetPriorityThread
tech.root: storage
title: StorPortSetPriorityThread
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: 
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
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - storport.h
api_name:
 - StorPortSetPriorityThread
f1_keywords:
 - StorPortSetPriorityThread
 - storport/StorPortSetPriorityThread
dev_langs:
 - c++
---

## -description

**StorPortSetPriorityThread** sets the run-time priority of a miniport-created thread.

## -parameters

### -param HwDeviceExtension

[in] Pointer to the miniport's hardware device extension.

### -param ThreadContext

[in] Pointer to the thread context received in a prior call to [**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md).

### -param Priority

[in] A [**STOR_THREAD_PRIORITY**](ne-storport-stor_thread_priority.md) enum value that specifies the thread priority to set.

## -returns

**StorPortSetPriorityThread** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_SUCCESS | The specified thread priority was set successfully. |
| STOR_STATUS_INVALID_IRQL | IRQL level must equal PASSIVE_LEVEL. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the provided parameters are invalid. |
| STOR_STATUS_UNSUCCESSFUL | Returned for other internal system reasons. |

## -remarks

A miniport can call **StorPortSetPriorityThread** to change the priority of the thread specified by **ThreadContext**.

Threads, whatever their respective run-time priorities, are run at IRQL = PASSIVE_LEVEL. See [Thread Priorities](/windows-hardware/drivers/kernel/thread-priorities) for more information.

A miniport should specify a thread priority value that avoids run-time priority inversions. See [Device-dedicated Threads](/windows-hardware/drivers/kernel/device-dedicated-threads) for more information.

## -see-also

[**STOR_THREAD_PRIORITY**](ne-storport-stor_thread_priority.md)

[**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md)
