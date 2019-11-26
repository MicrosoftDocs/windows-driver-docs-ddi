---
UID: NF:storport.StorPortSetEvent
title: StorPortSetEvent function
author: windows-driver-content
description: TBD
tech.root:
ms.assetid: 85d89cc8-a4b6-4f83-a3ba-2c64d28ca516
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: function
ms.keywords: StorPortSetEvent
req.header: storport.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
- StorPortSetEvent
product: 
- Windows
targetos: Windows

---

# StorPortSetEvent function

## -description

**StorPortSetEvent** sets an event object to the signaled state.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport's device extension.

### -param Event

Pointer to a [STOR_EVENT](ns-storport-stor_event.md) structure containing the event object.

## -returns

**StorPortSetEvent** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| STOR_STATUS_UNSUCCESSFUL | The operation failed. |
| STOR_STATUS_SUCCESS | The event object was successfully set to the signaled state. |
| STOR_STATUS_INVALID_PARAMETER | Either *HwDeviceExtension* or *Event* are invalid parameters. |

## -remarks

<!-- ????????????????????? -->

## -see-also

[STOR_EVENT](ns-storport-stor_event.md)

[**StorPortInitializeEvent**](ns-storport-storport_initialize_event.md)