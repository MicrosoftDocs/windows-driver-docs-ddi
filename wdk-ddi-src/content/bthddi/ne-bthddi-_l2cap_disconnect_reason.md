---
UID: NE:bthddi._L2CAP_DISCONNECT_REASON
title: _L2CAP_DISCONNECT_REASON
author: windows-driver-content
description: The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been disconnected.
old-location: bltooth\l2cap_disconnect_reason.htm
old-project: bltooth
ms.assetid: 34a37d29-c517-45dc-b94d-abffaa91cb31
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _L2CAP_DISCONNECT_REASON, L2CAP_DISCONNECT_REASON
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: L2CAP_DISCONNECT_REASON
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
req.typenames: L2CAP_DISCONNECT_REASON
---

# _L2CAP_DISCONNECT_REASON enumeration



## -description
The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been
  disconnected.



## -syntax

````
typedef enum _L2CAP_DISCONNECT_REASON { 
  HciDisconnect           = 0,
  L2capDisconnectRequest  = 1,
  RadioPoweredDown        = 2,
  HardwareRemoval         = 3
} L2CAP_DISCONNECT_REASON;
````


## -enum-fields

### -field HciDisconnect

The value specifies for the profile driver that the Bluetooth driver stack has received a
     disconnect notification from the host controller interface (HCI) layer.


### -field L2capDisconnectRequest

This value specifies for the profile driver that a disconnect request has been received from a
     remote device.


### -field RadioPoweredDown

This value specifies for the profile driver that the local radio has been turned off.


### -field HardwareRemoval

This value specifies for the profile driver that the local radio has been physically
     removed.


## -remarks
A value from this enumeration is used as the 
    <b>Reason</b> member of the 
    <a href="..\bthddi\ns-bthddi-_indication_parameters.md">INDICATION_PARAMETERS</a> structure.

Hardware limitations may prevent the Bluetooth driver stack from distinguishing between 
    <b>RadioPoweredDown</b> and 
    <b>HardwareRemoval</b> events.

Currently, 
    <i>HciDisconnect</i> and 
    <i>L2capDisconnectRequest</i> are the only values the Bluetooth driver stack passes to the 
    <a href="..\bthddi\nc-bthddi-pfnbthport_indication_callback.md">L2CAP Callback Function</a>.


## -see-also
<dl>
<dt>
<a href="..\bthddi\ns-bthddi-_indication_parameters.md">INDICATION_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20L2CAP_DISCONNECT_REASON enumeration%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

