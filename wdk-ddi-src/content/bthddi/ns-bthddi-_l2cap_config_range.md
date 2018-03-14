---
UID: NS:bthddi._L2CAP_CONFIG_RANGE
title: "_L2CAP_CONFIG_RANGE"
author: windows-driver-content
description: The L2CAP_CONFIG_RANGE structure is used to specify a range of possible values for the FlushTO member of the _BRB_L2CA_OPEN_CHANNEL structure during incoming requests.
old-location: bltooth\l2cap_config_range.htm
old-project: bltooth
ms.assetid: 95f288ea-a32a-478f-870b-5aa6ff1edf44
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PL2CAP_CONFIG_RANGE, L2CAP_CONFIG_RANGE, L2CAP_CONFIG_RANGE structure [Bluetooth Devices], PL2CAP_CONFIG_RANGE, PL2CAP_CONFIG_RANGE structure pointer [Bluetooth Devices], _L2CAP_CONFIG_RANGE, bltooth.l2cap_config_range, bth_structs_86178813-5f20-4c58-8d70-c863217350b3.xml, bthddi/L2CAP_CONFIG_RANGE, bthddi/PL2CAP_CONFIG_RANGE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	L2CAP_CONFIG_RANGE
product: Windows
targetos: Windows
req.typenames: L2CAP_CONFIG_RANGE, *PL2CAP_CONFIG_RANGE
---

# _L2CAP_CONFIG_RANGE structure


## -description


The L2CAP_CONFIG_RANGE structure is used to specify a range of possible values for the 
  <b>FlushTO</b> member of the 
  <a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a> structure during
  incoming requests.


## -syntax


````
typedef struct _L2CAP_CONFIG_RANGE {
  USHORT Min;
  USHORT Max;
} L2CAP_CONFIG_RANGE, *PL2CAP_CONFIG_RANGE;
````


## -struct-fields




### -field Min

The minimum value that the local system can accept.


### -field Max

The maximum value that the local system can accept.


## -remarks



The L2CAP_CONFIG_RANGE structure contains the range of values that the profile driver uses to
    negotiate a flush timeout when a remote device contacts the profile driver to request a L2CAP connection.
    Profile drivers build and send a <b>BRB_L2CA_OPEN_CHANNEL_RESPONSE</b> request to either accept or reject the
    settings sent by the requesting device. If the preferred value that is sent by the requesting device
    falls in the range specified by this structure's 
    <b>Min</b> and 
    <b>Max</b> members, the 
    <b>FlushTO</b> settings are accepted. If the profile driver rejects the setting as being too long, the
    profile driver responds with the value of the 
    <b>Max</b> member, the maximum setting it will accept. If this value falls within the range requested by
    the remote device, the 
    <b>FlushTO</b> value is accepted. Otherwise, the profile driver rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

If the profile driver rejects the remote device's preferred timeout value as being too short, the
    profile driver responds with the value of the 
    <b>Min</b> member value, the minimum setting it will accept. If the profile driver's minimum flush timeout
    falls within the range requested by the remote device, the profile driver accepts the 
    <b>FlushTO</b> value. Otherwise, the profile driver rejects the 
    <b>FlushTO</b> value and the connection attempt fails.

A profile driver negotiates these values separately from the flush timeout settings it requests when
    it attempts to open an outbound channel to a remote device using the <b>BRB_L2CA_OPEN_CHANNEL</b> request. For
    more information about value ranges, see 
    <a href="..\bthddi\ns-bthddi-_l2cap_config_value_range.md">L2CAP_CONFIG_VALUE_RANGE</a>.




## -see-also

<a href="..\bthddi\ns-bthddi-_l2cap_config_value_range.md">L2CAP_CONFIG_VALUE_RANGE</a>



<a href="..\bthddi\ns-bthddi-_brb_l2ca_open_channel.md">_BRB_L2CA_OPEN_CHANNEL</a>



 

 


