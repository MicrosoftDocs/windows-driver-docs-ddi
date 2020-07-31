---
UID: NE:poscx._POS_CX_EVENT_ATTRIBUTES
title: _POS_CX_EVENT_ATTRIBUTES (poscx.h)
description: The POS_CX_EVENT_ATTRIBUTES describes the priority and access rights for the POS events coming from the device. The values are a combination of the values defined in POS_CX_EVENT_DEST and POS_CX_EVENT_PRIORITY.
old-location: pos\pos_cx_event_attributes.htm
tech.root: pos
ms.assetid: 5B8B38B6-ACF3-44F9-BC83-71F0A2FC4DDD
ms.date: 02/23/2018
keywords: ["_POS_CX_EVENT_ATTRIBUTES enumeration"]
ms.keywords: POS_CX_EVENT_ATTRIBUTES, POS_CX_EVENT_ATTRIBUTES enumeration, POS_CX_EVENT_ATTR_BCAST_CONTROL, POS_CX_EVENT_ATTR_CONTROL, POS_CX_EVENT_ATTR_DATA, _POS_CX_EVENT_ATTRIBUTES, pos.pos_cx_event_attributes, poscx/POS_CX_EVENT_ATTRIBUTES, poscx/POS_CX_EVENT_ATTR_BCAST_CONTROL, poscx/POS_CX_EVENT_ATTR_CONTROL, poscx/POS_CX_EVENT_ATTR_DATA
f1_keywords:
 - "poscx/POS_CX_EVENT_ATTRIBUTES"
 - "POS_CX_EVENT_ATTRIBUTES"
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
- POS_CX_EVENT_ATTRIBUTES
targetos: Windows
req.typenames: POS_CX_EVENT_ATTRIBUTES
req.product: Windows 10 or later.
---

# _POS_CX_EVENT_ATTRIBUTES enumeration


## -description


The POS_CX_EVENT_ATTRIBUTES describes the priority and access rights for the POS events coming from the device. The values are a combination of the values defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_dest">POS_CX_EVENT_DEST</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_priority">POS_CX_EVENT_PRIORITY</a>.


## -enum-fields




### -field POS_CX_EVENT_ATTR_DATA

Data level priority delivered in FIFO to the claim owner handle.


### -field POS_CX_EVENT_ATTR_CONTROL

Control level priority delivered in FIFO to the claim owner handle.


### -field POS_CX_EVENT_ATTR_BCAST_CONTROL

Control level priority delivered in FIFO to ALL open handles on the driver.


## -remarks



<div class="alert"><b>Note</b>  PosCx will deliver all Control level events before Data level events.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_dest">POS_CX_EVENT_DEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/ne-poscx-_pos_cx_event_priority">POS_CX_EVENT_PRIORITY</a>
 

 

