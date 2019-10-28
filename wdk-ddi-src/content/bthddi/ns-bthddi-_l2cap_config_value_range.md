---
UID: NS:bthddi._L2CAP_CONFIG_VALUE_RANGE
title: _L2CAP_CONFIG_VALUE_RANGE (bthddi.h)
description: The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the Mtu and FlushTO members of the _BRB_L2CA_OPEN_CHANNEL structure.
old-location: bltooth\l2cap_config_value_range.htm
tech.root: bltooth
ms.assetid: 12d9b0c1-6dce-4dc6-a8df-706408e1fbe1
ms.date: 04/27/2018
ms.keywords: "*PL2CAP_CONFIG_VALUE_RANGE, L2CAP_CONFIG_VALUE_RANGE, L2CAP_CONFIG_VALUE_RANGE structure [Bluetooth Devices], PL2CAP_CONFIG_VALUE_RANGE, PL2CAP_CONFIG_VALUE_RANGE structure pointer [Bluetooth Devices], _L2CAP_CONFIG_VALUE_RANGE, bltooth.l2cap_config_value_range, bth_structs_3af526a5-d36e-432f-9d2e-fa31bee0effe.xml, bthddi/L2CAP_CONFIG_VALUE_RANGE, bthddi/PL2CAP_CONFIG_VALUE_RANGE"
ms.topic: struct
f1_keywords:
 - "bthddi/L2CAP_CONFIG_VALUE_RANGE"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
- L2CAP_CONFIG_VALUE_RANGE
product:
- Windows
targetos: Windows
req.typenames: L2CAP_CONFIG_VALUE_RANGE, *PL2CAP_CONFIG_VALUE_RANGE
---

# _L2CAP_CONFIG_VALUE_RANGE structure


## -description


The L2CAP_CONFIG_VALUE_RANGE structure is used to specify values for the 
  <b>Mtu</b> and 
  <b>FlushTO</b> members of the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a> structure.


## -struct-fields




### -field Min

The minimum value that the local system will accept.


### -field Preferred

The ideal value that the local system requests that the remote device accept.


### -field Max

The maximum value that the local system will accept.


## -remarks



For 
    <b>FlushTO</b> member settings, the L2CAP_CONFIG_VALUE_RANGE structure contains the profile driver's ideal
    flush timeout value in the 
    <b>Preferred</b> member, along with a range of acceptable values as specified by the 
    <b>Min</b> and 
    <b>Max</b> members.

The profile driver uses a <b>BRB_L2CA_OPEN_CHANNEL</b> request to send these settings to a remote device with
    which it is attempting to create a L2CAP connection. If the 
    <b>Preferred</b> value that is sent by the profile driver falls in the range specified by the remote
    device, the 
    <b>FlushTO</b> settings are accepted. If the remote device rejects the setting as being too long, the
    remote device responds with the maximum setting it will accept. If the remote device's maximum flush
    timeout falls within the range defined by the 
    <b>Min</b> and 
    <b>Max</b> members, the 
    <b>FlushTO</b> value is accepted. Otherwise, the remote device rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

If the remote device rejects the profile driver's 
    <b>Preferred</b> member value as being too short, the remote device responds with the minimum settings it
    will accept. If the remote device's minimum flush timeout falls within the range defined by the 
    <b>Min</b> and 
    <b>Max</b> members, the 
    <b>FlushTO</b> value is accepted. Otherwise, the remote device rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

The profile driver negotiates these values separately from the flush timeout settings that it sends to
    the Bluetooth driver stack when a remote device attempts to create an inbound L2CAP channel to the
    profile driver. For more information about L2CAP configuration ranges, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_l2cap_config_range">L2CAP_CONFIG_RANGE</a>.

For 
    <b>Mtu</b> members settings, this structure provides 
    <b>Preferred</b>, 
    <b>Min</b>, and 
    <b>Max</b> settings for both inbound and outbound connections.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_l2ca_open_channel">_BRB_L2CA_OPEN_CHANNEL</a>
 

 

