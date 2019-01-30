---
UID: NE:bthddi._L2CAP_DISCONNECT_REASON
title: "_L2CAP_DISCONNECT_REASON" (bthddi.h)
description: The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been disconnected.
old-location: bltooth\l2cap_disconnect_reason.htm
tech.root: bltooth
ms.assetid: 34a37d29-c517-45dc-b94d-abffaa91cb31
ms.date: 04/27/2018
ms.keywords: HardwareRemoval, HciDisconnect, L2CAP_DISCONNECT_REASON, L2CAP_DISCONNECT_REASON enumeration [Bluetooth Devices], L2capDisconnectRequest, RadioPoweredDown, _L2CAP_DISCONNECT_REASON, bltooth.l2cap_disconnect_reason, bth_enums_b465d42e-515c-49b9-8d6c-0d576853a41b.xml, bthddi/HardwareRemoval, bthddi/HciDisconnect, bthddi/L2CAP_DISCONNECT_REASON, bthddi/L2capDisconnectRequest, bthddi/RadioPoweredDown
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista and later versions of Windows.
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
-	bthddi.h
api_name:
-	L2CAP_DISCONNECT_REASON
product:
- Windows
targetos: Windows
req.typenames: L2CAP_DISCONNECT_REASON
---

# _L2CAP_DISCONNECT_REASON enumeration


## -description


The L2CAP_DISCONNECT_REASON enumeration type gives the reason an L2CAP channel has been
  disconnected.


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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536680">INDICATION_PARAMETERS</a> structure.

Hardware limitations may prevent the Bluetooth driver stack from distinguishing between 
    <b>RadioPoweredDown</b> and 
    <b>HardwareRemoval</b> events.

Currently, 
    <i>HciDisconnect</i> and 
    <i>L2capDisconnectRequest</i> are the only values the Bluetooth driver stack passes to the 
    <a href="https://msdn.microsoft.com/d3ca900d-1dd6-49da-ae94-855de3fbd086">L2CAP Callback Function</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536680">INDICATION_PARAMETERS</a>
 

 

