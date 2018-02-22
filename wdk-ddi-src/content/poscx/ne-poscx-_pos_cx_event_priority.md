---
UID: NE:poscx._POS_CX_EVENT_PRIORITY
title: "_POS_CX_EVENT_PRIORITY"
author: windows-driver-content
description: The POS_CX_EVENT_PRIORITY defines the importance of the event and the order it will be delivered to the client application.
old-location: pos\pos_cx_event_priority.htm
old-project: pos
ms.assetid: 835DC1E4-2D49-4D43-A545-5D4288412EC6
ms.author: windowsdriverdev
ms.date: 2/19/2018
ms.keywords: POS_CX_EVENT_PRIORITY_INVALID, pos.pos_cx_event_priority, POS_CX_EVENT_PRIORITY_DATA, poscx/POS_CX_EVENT_PRIORITY_DATA, poscx/POS_CX_EVENT_PRIORITY_INVALID, POS_CX_EVENT_PRIORITY, poscx/POS_CX_EVENT_PRIORITY, _POS_CX_EVENT_PRIORITY, POS_CX_EVENT_PRIORITY enumeration, POS_CX_EVENT_PRIORITY_CONTROL, poscx/POS_CX_EVENT_PRIORITY_CONTROL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	POS_CX_EVENT_PRIORITY
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# _POS_CX_EVENT_PRIORITY enumeration


## -description


The POS_CX_EVENT_PRIORITY defines the importance of the event and the order it will be delivered to the client application.


## -syntax


````
typedef enum _POS_CX_EVENT_PRIORITY { 
  POS_CX_EVENT_PRIORITY_INVALID  = 0,
  POS_CX_EVENT_PRIORITY_DATA     = 1,
  POS_CX_EVENT_PRIORITY_CONTROL  = 2
} POS_CX_EVENT_PRIORITY;
````


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


