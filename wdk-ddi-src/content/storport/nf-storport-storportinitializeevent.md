---
UID: NF:storport.StorPortInitializeEvent
title: StorPortInitializeEvent function
author: windows-driver-content
description: StorPortInitializeEvent initializes an event object as a synchronization or notification type event, and sets it to a signaled or not-signaled state.
tech.root: storage
ms.assetid: fb3aa321-9b9c-4138-8180-76bb8ed07748
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: function
ms.keywords: StorPortInitializeEvent
req.header: storport.h
f1_keywords:
 - "storport/StorPortInitializeEvent"
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
- StorPortInitializeEvent
product: 
- Windows
targetos: Windows

---

# StorPortInitializeEvent function

## -description

**StorPortInitializeEvent** initializes an event object as a synchronization or notification type event, and sets it to a signaled or not-signaled state.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's hardware device extension.

### -param Event

Pointer to a [STOR_EVENT](ns-storport-stor_event.md) structure that describes the event object.

### -param Type

A [STOR_EVENT_TYPE](ne-storport-stor_event_type.md) enum that identifies the event type.

### -param State

Boolean value that specifies the initial state of the event.

## -returns

**StorPortInitializeEvent** returns STOR_STATUS_SUCCESS on success. It returns STOR_STATUS_INVALID_PARAMETER if any of the parameters are invalid.

## -remarks

A miniport can call **StorPortInitializeEvent** to initialize an event object as a synchronization or notification-type event, and set the event object to a signaled or not-signaled state.

<!-- I TOOK THIS FROM KeInitializeEvent PAGE - it probably needs to be revamped to be storage/miniport-specific: -->

Miniport drivers typically use a notification event type to wait for an I/O operation <!-- should this be a storage-specific kind of operation? --> to complete. When a notification event is set to the signaled state, all threads that were waiting for the event to be set to the signaled state become eligible for execution. The event remains in the signaled state until a thread calls <!-- which function(s)??? --> to set the event in the not-signaled state.

A synchronization event is also called an autoreset or autoclearing event, because its signaled state is automatically reset to the not-signaled state each time a wait is satisfied. When a synchronization event is set to the signaled state, a single thread that is waiting for the event to be reset to not-signaled becomes eligible for execution. The kernel automatically resets the event to the not-signaled state each time a wait is satisfied. A miniport driver can use a synchronization event to protect a shared resource that is used in synchronizing the operations of several threads. Sync events are rarely used<!-- ???????? -->

<!-- For more information about event objects, see [Event Objects](https://docs.microsoft.com/windows-hardware/drivers/kernel/event-objects) -->

## -see-also

[STOR_EVENT](ns-storport-stor_event.md)

[STOR_EVENT_TYPE](ne-storport-stor_event_type.md)

[**StorPortSetEvent**](nf-storport-storportsetevent.md)

[**StoPortWaitForSingleObject**](nf-storport-storportwaitforsingleobject.md)
