---
UID: NF:poscx.PosCxGetPendingEvent
title: PosCxGetPendingEvent function
author: windows-driver-content
description: PosCxGetPendingEvent is called either from the device read callback, or when a new event arrives.
old-location: pos\poscxgetpendingevent.htm
tech.root: pos
ms.assetid: D68C24E4-DCFB-44F6-92EE-9FF4A1A52841
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosCxGetPendingEvent, PosCxGetPendingEvent function, pos.poscxgetpendingevent, poscx/PosCxGetPendingEvent
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	PosCxGetPendingEvent
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxGetPendingEvent function


## -description


      PosCxGetPendingEvent is called either from the device read callback, or when a new 

      event arrives. The function searches the pending events database for events that are waiting for the caller that issued the request.  

      It first searches the control pending events database, and then the data pending event database.


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param request [in]

A handle to a framework request object that represents the read request if <b>PosCxGetPendingEvent</b> is called from the device read callback.


## -returns



Possible return values are:

<table>
<tr>
<td><b>STATUS_SUCCESS</b></td>
<td>The request was completed by PosCx. The caller  must not complete the request in this case.</td>
</tr>
<tr>
<td><b>STATUS_PENDING</b></td>
<td>No events are currently available for the caller. The request will be completed by PosCx in the future. The caller must not complete the request in this case.</td>
</tr>
<tr>
<td><b>STATUS_DEVICE_NOT_READY</b></td>
<td>The PosCx library was not successfully initialized. The caller should complete the request.</td>
</tr>
<tr>
<td>Other errors</td>
<td>Other appropriate failure error codes.  The caller should complete the request.</td>
</tr>
</table>
 



