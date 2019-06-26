---
UID: NE:bthddi._SCO_DISCONNECT_REASON
title: _SCO_DISCONNECT_REASON (bthddi.h)
description: The SCO_DISCONNECT_REASON enumeration type gives the reason an SCO channel has been disconnected.
old-location: bltooth\sco_disconnect_reason.htm
tech.root: bltooth
ms.assetid: bca4bfc6-d44f-4b10-a30a-ba2acefad7a9
ms.date: 04/27/2018
ms.keywords: "*PSCO_DISCONNECT_REASON, PSCO_DISCONNECT_REASON, PSCO_DISCONNECT_REASON enumeration pointer [Bluetooth Devices], SCO_DISCONNECT_REASON, SCO_DISCONNECT_REASON enumeration [Bluetooth Devices], ScoDisconnectRequest, ScoHardwareRemoval, ScoHciDisconnect, ScoRadioPoweredDown, _SCO_DISCONNECT_REASON, bltooth.sco_disconnect_reason, bth_enums_ea951efc-1250-4414-9592-2bffe239dc95.xml, bthddi/PSCO_DISCONNECT_REASON, bthddi/SCO_DISCONNECT_REASON, bthddi/ScoDisconnectRequest, bthddi/ScoHardwareRemoval, bthddi/ScoHciDisconnect, bthddi/ScoRadioPoweredDown"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bthddi.h
api_name:
- SCO_DISCONNECT_REASON
product:
- Windows
targetos: Windows
req.typenames: SCO_DISCONNECT_REASON, *PSCO_DISCONNECT_REASON
---

# _SCO_DISCONNECT_REASON enumeration


## -description


The SCO_DISCONNECT_REASON enumeration type gives the reason an SCO channel has been
  disconnected.


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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_sco_indication_parameters">
    SCO_INDICATION_PARAMETERS</a> structure.

Hardware limitations may prevent the Bluetooth driver stack from distinguishing between 
    <b>ScoRadioPoweredDown</b> and 
    <b>ScoHardwareRemoval</b> events.

Currently, 
    <i>ScoHciDisconnect</i> is the only value the Bluetooth driver stack passes to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnsco_indication_callback">SCO Callback Function</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/nc-bthddi-pfnsco_indication_callback">SCO Callback Function</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthddi/ns-bthddi-_sco_indication_parameters">SCO_INDICATION_PARAMETERS</a>
 

 

