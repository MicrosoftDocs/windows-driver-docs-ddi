---
UID: NE:poscx._POS_CX_EVENT_PRIORITY
title: _POS_CX_EVENT_PRIORITY (poscx.h)
description: The POS_CX_EVENT_PRIORITY defines the importance of the event and the order it will be delivered to the client application.
old-location: pos\pos_cx_event_priority.htm
tech.root: pos
ms.assetid: 835DC1E4-2D49-4D43-A545-5D4288412EC6
ms.date: 02/23/2018
keywords: ["POS_CX_EVENT_PRIORITY enumeration"]
ms.keywords: POS_CX_EVENT_PRIORITY, POS_CX_EVENT_PRIORITY enumeration, POS_CX_EVENT_PRIORITY_CONTROL, POS_CX_EVENT_PRIORITY_DATA, POS_CX_EVENT_PRIORITY_INVALID, _POS_CX_EVENT_PRIORITY, pos.pos_cx_event_priority, poscx/POS_CX_EVENT_PRIORITY, poscx/POS_CX_EVENT_PRIORITY_CONTROL, poscx/POS_CX_EVENT_PRIORITY_DATA, poscx/POS_CX_EVENT_PRIORITY_INVALID
f1_keywords:
 - "poscx/POS_CX_EVENT_PRIORITY"
 - "POS_CX_EVENT_PRIORITY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- poscx.h
api_name:
- POS_CX_EVENT_PRIORITY
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# _POS_CX_EVENT_PRIORITY enumeration


## -description


The POS_CX_EVENT_PRIORITY defines the importance of the event and the order it will be delivered to the client application.


## -enum-fields




### -field POS_CX_EVENT_PRIORITY_INVALID

Invalid priority. This value should not be used.


### -field POS_CX_EVENT_PRIORITY_DATA

Data level priority delivered in FIFO.


### -field POS_CX_EVENT_PRIORITY_CONTROL

Control level priority delivered in FIFO.


### -field POS_CX_EVENT_PRIORITY__MAX




## -remarks



<div class="alert"><b>Note</b>  PosCx will deliver all Control level events before Data level events.</div>
<div> </div>


