---
UID: NE:poscx._POS_CX_EVENT_ATTRIBUTES
title: _POS_CX_EVENT_ATTRIBUTES (poscx.h)
description: The POS_CX_EVENT_ATTRIBUTES describes the priority and access rights for the POS events coming from the device. The values are a combination of the values defined in POS_CX_EVENT_DEST and POS_CX_EVENT_PRIORITY.
tech.root: pos
ms.date: 11/17/2022
keywords: ["POS_CX_EVENT_ATTRIBUTES enumeration"]
ms.keywords: POS_CX_EVENT_ATTRIBUTES, POS_CX_EVENT_ATTRIBUTES enumeration, POS_CX_EVENT_ATTR_BCAST_CONTROL, POS_CX_EVENT_ATTR_CONTROL, POS_CX_EVENT_ATTR_DATA, _POS_CX_EVENT_ATTRIBUTES, pos.pos_cx_event_attributes, poscx/POS_CX_EVENT_ATTRIBUTES, poscx/POS_CX_EVENT_ATTR_BCAST_CONTROL, poscx/POS_CX_EVENT_ATTR_CONTROL, poscx/POS_CX_EVENT_ATTR_DATA
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
req.typenames: POS_CX_EVENT_ATTRIBUTES
req.product: Windows 10 or later.
f1_keywords:
 - _POS_CX_EVENT_ATTRIBUTES
 - poscx/_POS_CX_EVENT_ATTRIBUTES
 - POS_CX_EVENT_ATTRIBUTES
 - poscx/POS_CX_EVENT_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - _POS_CX_EVENT_ATTRIBUTES
 - POS_CX_EVENT_ATTRIBUTES
---

## -description

The POS_CX_EVENT_ATTRIBUTES enumeration describes the priority and access rights for the POS events coming from the device. The values are a combination of the values defined in [POS_CX_EVENT_DEST](/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_dest) and [POS_CX_EVENT_PRIORITY](/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_priority).

## -enum-fields

### -field POS_CX_EVENT_ATTR_DATA

Data level priority delivered in FIFO to the claim owner handle.

### -field POS_CX_EVENT_ATTR_CONTROL

Control level priority delivered in FIFO to the claim owner handle.

### -field POS_CX_EVENT_ATTR_BCAST_CONTROL

Control level priority delivered in FIFO to ALL open handles on the driver.

## -remarks

> [!NOTE]
> PosCx will deliver all Control level events before Data level events.

## -see-also

[POS_CX_EVENT_DEST](/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_dest)

[POS_CX_EVENT_PRIORITY](/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_priority)
