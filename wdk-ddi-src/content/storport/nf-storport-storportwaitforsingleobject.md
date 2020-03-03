---
UID: NF:storport.StorPortWaitForSingleObject
title: StorPortWaitForSingleObject function
author: windows-driver-content
description: A miniport can call StorPortWaitForSingleObject function to put the current thread into a wait state until the given dispatcher object is set to signaled state or optionally times out.
tech.root: storage
ms.assetid: 36dba4d1-de52-4522-ba07-f8b57357b48e
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: function
ms.keywords: StorPortWaitForSingleObject
req.header: storport.h
f1_keywords:
 - "storport/StorPortWaitForSingleObject"
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- 
api_location: 
- 
api_name: 
- StorPortWaitForSingleObject
product: 
- Windows
targetos: Windows

---

# StorPortWaitForSingleObject function

## -description

A miniport can call **StorPortWaitForSingleObject** function to put the current thread into a wait state until the given dispatcher object is set to signaled state or optionally times out.

## -parameters

### -param HwDeviceExtension

Pointer to the storage miniport's device extension.

### -param Object

Pointer to the initialized dispatcher object (event, mutex, semaphore, thread, or timer).   <!-- this is only just an event in storport? -->

### -param Alertable

Boolean value set TRUE if the wait is alertable and FALSE otherwise.

### -param Timeout

Pointer to the timeout value that specifies the absolute or relative time, in 100-nanosecond units, at which the wait is to be completed.

A positive value specifies an absolute time, relative to January 1, 1601. A negative value specifies an interval relative to the current time. Absolute expiration times track any changes in the system time; relative expiration times are not affected by system time changes.

If *Timeout* = 0, the routine returns without waiting. If the miniport supplies a NULL pointer, the routine waits indefinitely until the dispatcher object is set to the signaled state. For more information, see the following Remarks section. <!-- Should I copy remarks from KeWaitForSingleObject?? -->

## -returns

**StorPortSetEvent** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_UNSUCCESSFUL | The operation failed. |
| STOR_STATUS_SUCCESS | The ETW event was successfully logged. |
| STOR_STATUS_INVALID_PARAMETER | One or more of the parameters are invalid. |

## -remarks

<!-- Which remarks to copy from KeWaitForSingleObject?? For example: -->

Callers of **StorportWaitForSingleObject** must be running at IRQL <= DISPATCH_LEVEL. However, if *Timeout* = NULL or *Timeout* != 0, the caller must be running at IRQL <= APC_LEVEL and in a nonarbitrary thread context. (If *Timeout* != NULL and *Timeout* = 0, the caller must be running at IRQL <= DISPATCH_LEVEL.)

## -see-also

[**StorportInitializeEvent**](nf-storport-storportinitializeevent.md)

[**StorportSetEvent**](nf-storport-storportsetevent.md)

<!-- link to KeWaitForSingleObject? Any other links?->

