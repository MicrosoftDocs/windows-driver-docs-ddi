---
UID: NS:bthddi._BRB_L2CA_CLOSE_CHANNEL
title: _BRB_L2CA_CLOSE_CHANNEL (bthddi.h)
description: The _BRB_L2CA_CLOSE_CHANNEL structure describes an open L2CAP channel to close.
old-location: bltooth\_brb_l2ca_close_channel.htm
tech.root: bltooth
ms.assetid: 0a9f3720-8ae4-4219-a8b3-f1b88126f176
ms.date: 04/27/2018
keywords: ["_BRB_L2CA_CLOSE_CHANNEL structure"]
ms.keywords: "_BRB_L2CA_CLOSE_CHANNEL, _BRB_L2CA_CLOSE_CHANNEL structure [Bluetooth Devices], bltooth._brb_l2ca_close_channel, bth_structs_97d7dc1f-eb95-4cf3-8d21-a814622a0b81.xml, bthddi/_BRB_L2CA_CLOSE_CHANNEL"
f1_keywords:
 - "bthddi/_BRB_L2CA_CLOSE_CHANNEL"
 - "_BRB_L2CA_CLOSE_CHANNEL"
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
- _BRB_L2CA_CLOSE_CHANNEL
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_CLOSE_CHANNEL structure


## -description


The _BRB_L2CA_CLOSE_CHANNEL structure describes an open L2CAP channel to close.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ChannelHandle

The L2CAP channel handle that was returned by Bluetooth driver stack in response to an earlier 
     <a href="https://docs.microsoft.com/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a> or 
     <a href="https://docs.microsoft.com/previous-versions/ff536616(v=vs.85)">
     BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request. This is the channel handle to close.


## -remarks



To close a L2CAP channel, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536614(v=vs.85)">BRB_L2CA_CLOSE_CHANNEL</a> request.

A <b>BRB_L2CA_CLOSE_CHANNEL</b> request can be made for a channel that was initiated locally or remotely. If
    a profile driver has multiple L2CAP channels to a single remote device, it must close each one
    individually.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536614(v=vs.85)">BRB_L2CA_CLOSE_CHANNEL</a>



<a href="https://docs.microsoft.com/previous-versions/ff536615(v=vs.85)">BRB_L2CA_OPEN_CHANNEL</a>



<a href="https://docs.microsoft.com/previous-versions/ff536616(v=vs.85)">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>
 

 

