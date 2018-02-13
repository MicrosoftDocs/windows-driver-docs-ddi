---
UID: NE:bthddi._SCO_DISCONNECT_REASON
title: "_SCO_DISCONNECT_REASON"
author: windows-driver-content
description: The SCO_DISCONNECT_REASON enumeration type gives the reason an SCO channel has been disconnected.
old-location: bltooth\sco_disconnect_reason.htm
old-project: bltooth
ms.assetid: bca4bfc6-d44f-4b10-a30a-ba2acefad7a9
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: SCO_DISCONNECT_REASON, ScoHardwareRemoval, ScoDisconnectRequest, ScoHciDisconnect, bthddi/PSCO_DISCONNECT_REASON, bthddi/ScoHciDisconnect, PSCO_DISCONNECT_REASON enumeration pointer [Bluetooth Devices], _SCO_DISCONNECT_REASON, *PSCO_DISCONNECT_REASON, SCO_DISCONNECT_REASON enumeration [Bluetooth Devices], bthddi/SCO_DISCONNECT_REASON, PSCO_DISCONNECT_REASON, bthddi/ScoDisconnectRequest, bth_enums_ea951efc-1250-4414-9592-2bffe239dc95.xml, bltooth.sco_disconnect_reason, bthddi/ScoHardwareRemoval, bthddi/ScoRadioPoweredDown, ScoRadioPoweredDown
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	SCO_DISCONNECT_REASON
product: Windows
targetos: Windows
req.typenames: "*PSCO_DISCONNECT_REASON, SCO_DISCONNECT_REASON"
---

# _SCO_DISCONNECT_REASON enumeration


## -description


The SCO_DISCONNECT_REASON enumeration type gives the reason an SCO channel has been
  disconnected.


## -syntax


````
typedef enum _SCO_DISCONNECT_REASON { 
  ScoHciDisconnect      = 0,
  ScoDisconnectRequest  = 1,
  ScoRadioPoweredDown   = 2,
  ScoHardwareRemoval    = 3
} SCO_DISCONNECT_REASON, *PSCO_DISCONNECT_REASON;
````


## -enum-fields




### -field ScoHciDisconnect

This value specifies to the profile driver that the Bluetooth driver stack has received a
     disconnect notification from the host controller interface (HCI) layer.


### -field ScoDisconnectRequest

This value specifies to the profile driver that a disconnect request has been received from the
     remote device.


### -field ScoRadioPoweredDown

This value specifies to the profile driver that the local radio has been turned off.


### -field ScoHardwareRemoval

This value specifies to the profile driver that the local radio has been physically
     removed.


## -remarks



A value from this enumeration is used as the 
    <b>Reason</b> member of the 
    <a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">
    SCO_INDICATION_PARAMETERS</a> structure.

Hardware limitations may prevent the Bluetooth driver stack from distinguishing between 
    <b>ScoRadioPoweredDown</b> and 
    <b>ScoHardwareRemoval</b> events.

Currently, 
    <i>ScoHciDisconnect</i> is the only value the Bluetooth driver stack passes to the 
    <a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>.




## -see-also

<a href="..\bthddi\ns-bthddi-_sco_indication_parameters.md">SCO_INDICATION_PARAMETERS</a>



<a href="..\bthddi\nc-bthddi-pfnsco_indication_callback.md">SCO Callback Function</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20SCO_DISCONNECT_REASON enumeration%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

