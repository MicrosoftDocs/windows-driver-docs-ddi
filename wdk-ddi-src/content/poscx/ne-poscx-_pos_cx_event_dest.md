---
UID: NE:poscx._POS_CX_EVENT_DEST
title: _POS_CX_EVENT_DEST (poscx.h)
description: The POS_CX_EVENT_DEST defines which applications receive this event.
old-location: pos\pos_cx_event_dest.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["POS_CX_EVENT_DEST enumeration"]
ms.keywords: POS_CX_EVENT_DEST, POS_CX_EVENT_DEST enumeration, POS_CX_EVENT_DEST_ALL, POS_CX_EVENT_DEST_DEVICE_OWNER, POS_CX_EVENT_DEST_INVALID, _POS_CX_EVENT_DEST, pos.pos_cx_event_dest, poscx/POS_CX_EVENT_DEST, poscx/POS_CX_EVENT_DEST_ALL, poscx/POS_CX_EVENT_DEST_DEVICE_OWNER, poscx/POS_CX_EVENT_DEST_INVALID
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
req.typenames: POS_CX_EVENT_DEST
f1_keywords:
 - _POS_CX_EVENT_DEST
 - poscx/_POS_CX_EVENT_DEST
 - POS_CX_EVENT_DEST
 - poscx/POS_CX_EVENT_DEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - _POS_CX_EVENT_DEST
 - POS_CX_EVENT_DEST
---

# _POS_CX_EVENT_DEST enumeration


## -description

The POS_CX_EVENT_DEST defines which applications receive this event.

## -enum-fields

### -field POS_CX_EVENT_DEST_INVALID

Specifies that no devices will receive this event.  This value should not be used.

### -field POS_CX_EVENT_DEST_DEVICE_OWNER

Specifies that only the current claim owner will receive this event.

### -field POS_CX_EVENT_DEST_ALL

Specifies that the event will be broadcast to all client handles.

### -field POS_CX_EVENT_DEST__MAX

