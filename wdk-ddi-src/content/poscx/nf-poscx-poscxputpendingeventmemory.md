---
UID: NF:poscx.PosCxPutPendingEventMemory
title: PosCxPutPendingEventMemory function (poscx.h)
description: PosCxPutPendingEventMemory tries to delegate a memory object containing the event data to a waiting caller.
tech.root: pos
ms.date: 03/07/2023
keywords: ["PosCxPutPendingEventMemory function"]
ms.keywords: PosCxPutPendingEventMemory, PosCxPutPendingEventMemory function, pos.poscxputpendingeventmemory, poscx/PosCxPutPendingEventMemory
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
 - PosCxPutPendingEventMemory
 - poscx/PosCxPutPendingEventMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxPutPendingEventMemory
---

## -description

PosCxPutPendingEventMemory tries to delegate a memory object containing the event data to a waiting caller. If the target caller does not have a read request waiting, the new event is added to      the designated event queue (control or data).

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param deviceInterfaceTag [in]

The device interface associated with the event.  By default, only file objects that have the same tag will receive this event.

### -param eventMemory [in]

The new event data memory object that contains both the point-of-service event header and the data. PosCx will take over ownership of this passed in memory object.

### -param eventAttr [in]

The event attributes.

## -returns

Possible return values are:

| Value | Description |
|---|---|
| **STATUS_SUCCESS** | The event was created and delegated to a waiting caller, or the event was discarded because there is no device owner. |
| **STATUS_PENDING** | The event was queued because no caller is currently waiting. |
| **STATUS_DEVICE_NOT_READY** | The PosCx library was not successfully initialized. |
| Other errors | Other appropriate failure error codes. |

## -see-also

[POS_CX_EVENT_ATTRIBUTES](./ne-poscx-_pos_cx_event_attributes.md)