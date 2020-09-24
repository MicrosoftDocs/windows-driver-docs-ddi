---
UID: NF:storport.StorPortSetEvent
title: StorPortSetEvent function
description: A miniport can call StorPortSetEvent to set an event object to the signaled state.
tech.root: storage
ms.assetid: 85d89cc8-a4b6-4f83-a3ba-2c64d28ca516
ms.date: 03/24/2020
ms.topic: function
ms.keywords: StorPortSetEvent
req.header: storport.h
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
targetos: Windows
f1_keywords:
 - StorPortSetEvent
 - storport/StorPortSetEvent
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortSetEvent
product:
 - Windows
---

# StorPortSetEvent function


## -description

A miniport can call **StorPortSetEvent** to set an event object to the signaled state.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's device extension.

### -param Event

Pointer to a [**STOR_EVENT**](ns-storport-stor_event.md) structure containing the event object.

## -returns

**StorPortSetEvent** returns a status code such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_INVALID_IRQL | The current IRQL is greater than DISPATCH_LEVEL. |
| STOR_STATUS_INVALID_PARAMETER | Either *HwDeviceExtension* or *Event* are invalid parameters. |
| STOR_STATUS_SUCCESS | The event object was successfully set to the signaled state. |
| STOR_STATUS_UNSUCCESSFUL | The operation failed. |

## -remarks

See [**KeSetEvent**](../wdm/nf-wdm-kesetevent.md) for more details.

## -see-also

[**KeSetEvent**](../wdm/nf-wdm-kesetevent.md) for more details.

[**STOR_EVENT**](ns-storport-stor_event.md)

[**StorPortInitializeEvent**](ns-storport-storport_initialize_event.md)