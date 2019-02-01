---
UID: NF:poscx.PosCxPutPendingEvent
title: PosCxPutPendingEvent function (poscx.h)
description: PosCxPutPendingEvent creates a new event object, copies the event data to the new event object, and tries to delegate it to the waiting caller.
old-location: pos\poscxputpendingevent.htm
tech.root: pos
ms.assetid: 4E2EA8F5-2D4A-4AEB-AF59-97D6C3FB09BC
ms.date: 02/23/2018
ms.keywords: PosCxPutPendingEvent, PosCxPutPendingEvent function, pos.poscxputpendingevent, poscx/PosCxPutPendingEvent
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	poscx.h
api_name:
-	PosCxPutPendingEvent
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxPutPendingEvent function


## -description


PosCxPutPendingEvent creates a new event object, copies the event data to the
      new event object, and tries to delegate it to the waiting caller. 
      If the target caller does not have a read request waiting, the new event is added to 
      the designated event queue (control or data).


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param deviceInterfaceTag [in]

The device interface associated with the event.  By default, only
          file objects that have the same tag will receive this event.


### -param eventType [in]

The new event type.


### -param rawEventDataSize [in]

The raw event (without point-of-service header) buffer size in bytes.


### -param rawEventDataPtr

The pointer to the raw (without point-of-service header) event data.
          The caller may reuse/release <i>rawEventDataPtr</i> after <b>PosCxPutPendingEvent</b> returns.


### -param eventAttr [in]

The event attributes.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The event was created and delegated to a waiting caller,
          or the event was discarded because there is no device owner.
</td>
</tr>
<tr>
<td><b>STATUS_PENDING</b></td>
<td>The event was queued because no caller is currently waiting.</td>
</tr>
<tr>
<td>Other errors</td>
<td>Other appropriate failure error codes.</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt593142">POS_CX_EVENT_ATTRIBUTES</a>
 

 

