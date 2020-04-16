---
UID: NF:storport.StorPortInitializeEvent
title: StorPortInitializeEvent function
author: windows-driver-content
description: StorPortInitializeEvent initializes an event object as a synchronization or notification type event, and sets it to a signaled or not-signaled state.
tech.root: storage
ms.assetid: fb3aa321-9b9c-4138-8180-76bb8ed07748
ms.author: windowsdriverdev
ms.date: 03/24/2020
ms.topic: function
ms.keywords: StorPortInitializeEvent
req.header: storport.h
f1_keywords:
 - "storport/StorPortInitializeEvent"
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 2004
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

Pointer to a caller-allocated [**STOR_EVENT**](ns-storport-stor_event.md) structure that describes the event object.

### -param Type

A [**STOR_EVENT_TYPE**](ne-storport-stor_event_type.md) enum that identifies the event type.

### -param State

Boolean value that specifies the initial state of the event.

## -returns

**StorPortInitializeEvent** returns STOR_STATUS_SUCCESS on success. It returns STOR_STATUS_INVALID_PARAMETER if any of the parameters are invalid.

## -remarks

A miniport can call **StorPortInitializeEvent** to initialize an event object as a synchronization or notification-type event, and set the event object to a signaled or not-signaled state.

See [**KeInitializeEvent**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent) for more details.

## -see-also

[**KeInitializeEvent**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializeevent)

[**STOR_EVENT**](ns-storport-stor_event.md)

[**STOR_EVENT_TYPE**](ne-storport-stor_event_type.md)

[**StorPortSetEvent**](nf-storport-storportsetevent.md)

[**StoPortWaitForSingleObject**](nf-storport-storportwaitforsingleobject.md)
