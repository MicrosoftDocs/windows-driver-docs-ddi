---
UID: NF:poscx.PosCxGetPendingEvent
title: PosCxGetPendingEvent function (poscx.h)
description: PosCxGetPendingEvent is called either from the device read callback, or when a new event arrives.
old-location: pos\poscxgetpendingevent.htm
tech.root: pos
ms.assetid: D68C24E4-DCFB-44F6-92EE-9FF4A1A52841
ms.date: 02/23/2018
keywords: ["PosCxGetPendingEvent function"]
ms.keywords: PosCxGetPendingEvent, PosCxGetPendingEvent function, pos.poscxgetpendingevent, poscx/PosCxGetPendingEvent
f1_keywords:
 - "poscx/PosCxGetPendingEvent"
 - "PosCxGetPendingEvent"
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
- PosCxGetPendingEvent
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxGetPendingEvent function

## -description

PosCxGetPendingEvent is called either from the device read callback, or when a new event arrives. The function searches the pending events database for events that are waiting for the caller that issued the request.  

It first searches the control pending events database, and then the data pending event database.

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param request [in]

A handle to a framework request object that represents the read request if **PosCxGetPendingEvent** is called from the device read callback.

## -returns

Possible return values are:

| Return value | Description |
| --- | --- |
| STATUS_SUCCESS | The request was completed by PosCx. The caller  must not complete the request in this case. |
| STATUS_PENDING | No events are currently available for the caller. The request will be completed by PosCx in the future. The caller must not complete the request in this case. |
| STATUS_DEVICE_NOT_READY | The PosCx library was not successfully initialized. The caller should complete the request. |
| Other errors | Other appropriate failure error codes.  The caller should complete the request. |
