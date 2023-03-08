---
UID: NF:poscx.PosCxPutPendingEvent
title: PosCxPutPendingEvent function (poscx.h)
description: PosCxPutPendingEvent creates a new event object, copies the event data to the new event object, and tries to delegate it to the waiting caller.
tech.root: pos
ms.date: 03/07/2023
keywords: ["PosCxPutPendingEvent function"]
ms.keywords: PosCxPutPendingEvent, PosCxPutPendingEvent function, pos.poscxputpendingevent, poscx/PosCxPutPendingEvent
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
f1_keywords:
 - PosCxPutPendingEvent
 - poscx/PosCxPutPendingEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxPutPendingEvent
---

## -description

PosCxPutPendingEvent creates a new event object, copies the event data to the new event object, and tries to delegate it to the waiting caller. If the target caller does not have a read request waiting, the new event is added to the designated event queue (control or data).

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param deviceInterfaceTag [in]

The device interface associated with the event.  By default, only file objects that have the same tag will receive this event.

### -param eventType [in]

The new event type.

### -param rawEventDataSize [in]

The raw event (without point-of-service header) buffer size in bytes.

### -param rawEventDataPtr

The pointer to the raw (without point-of-service header) event data. The caller may reuse/release *rawEventDataPtr* after **PosCxPutPendingEvent** returns.

### -param eventAttr [in]

The event attributes.

## -returns

Possible return values are:

| Value | Description |
|---|---|
| **STATUS_SUCCESS** | The event was created and delegated to a waiting caller, or the event was discarded because there is no device owner. |
| **STATUS_PENDING** | The event was queued because no caller is currently waiting. |
| Other errors | Other appropriate failure error codes. |

## -see-also

[POS_CX_EVENT_ATTRIBUTES](/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_attributes)
