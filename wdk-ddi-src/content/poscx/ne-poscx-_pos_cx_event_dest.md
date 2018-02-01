---
UID: NE:poscx._POS_CX_EVENT_DEST
title: "_POS_CX_EVENT_DEST"
author: windows-driver-content
description: The POS_CX_EVENT_DEST defines which applications receive this event.
old-location: pos\pos_cx_event_dest.htm
old-project: pos
ms.assetid: 63D16B9E-82CC-4171-B80A-D0FA6F2066E2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: POS_CX_EVENT_DEST enumeration, POS_CX_EVENT_DEST_INVALID, poscx/POS_CX_EVENT_DEST_INVALID, poscx/POS_CX_EVENT_DEST, poscx/POS_CX_EVENT_DEST_DEVICE_OWNER, POS_CX_EVENT_DEST, poscx/POS_CX_EVENT_DEST_ALL, pos.pos_cx_event_dest, POS_CX_EVENT_DEST_ALL, _POS_CX_EVENT_DEST, POS_CX_EVENT_DEST_DEVICE_OWNER
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
-	POS_CX_EVENT_DEST
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_DEST
req.product: Windows 10 or later.
---

# _POS_CX_EVENT_DEST enumeration


## -description


The POS_CX_EVENT_DEST defines which applications receive this event.


## -syntax


````
typedef enum _POS_CX_EVENT_DEST { 
  POS_CX_EVENT_DEST_INVALID       = 0,
  POS_CX_EVENT_DEST_DEVICE_OWNER  = 1,
  POS_CX_EVENT_DEST_ALL           = 2
} POS_CX_EVENT_DEST;
````


## -enum-fields




### -field POS_CX_EVENT_DEST_INVALID

Specifies that no devices will receive this event.  This value should not be used.


### -field POS_CX_EVENT_DEST_DEVICE_OWNER

Specifies that only the current claim owner will receive this event.


### -field POS_CX_EVENT_DEST_ALL

Specifies that the event will be broadcast to all client handles.


### -field POS_CX_EVENT_DEST__MAX



