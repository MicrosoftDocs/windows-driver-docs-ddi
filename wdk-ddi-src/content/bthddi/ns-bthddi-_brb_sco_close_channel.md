---
UID: NS:bthddi._BRB_SCO_CLOSE_CHANNEL
title: _BRB_SCO_CLOSE_CHANNEL (bthddi.h)
description: The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close.
old-location: bltooth\_brb_sco_close_channel.htm
tech.root: bltooth
ms.assetid: 1921cee1-411b-4fec-acfd-3380e84823b8
ms.date: 04/27/2018
keywords: ["_BRB_SCO_CLOSE_CHANNEL structure"]
ms.keywords: "_BRB_SCO_CLOSE_CHANNEL, _BRB_SCO_CLOSE_CHANNEL structure [Bluetooth Devices], bltooth._brb_sco_close_channel, bth_structs_d031efa4-0a68-47c0-8344-e95c677661c9.xml, bthddi/_BRB_SCO_CLOSE_CHANNEL"
f1_keywords:
 - "bthddi/_BRB_SCO_CLOSE_CHANNEL"
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
- _BRB_SCO_CLOSE_CHANNEL
product:
- Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_CLOSE_CHANNEL structure


## -description


The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close.


## -struct-fields




### -field Hdr

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The Bluetooth address of the remote device.


### -field ChannelHandle

The handle to the SCO channel to close.


## -remarks



To close a SCO channel, profile drivers should 
    <a href="https://docs.microsoft.com/previous-versions/ff536657(v=vs.85)">build and send</a> a 
    <a href="https://docs.microsoft.com/previous-versions/ff536622(v=vs.85)">BRB_SCO_CLOSE_CHANNEL</a> request.

A <b>BRB_SCO_CLOSE_CHANNEL</b> request can be made for a channel that was initiated locally or remotely. If a
    profile driver has multiple SCO connections to a single remote device, it must close each one
    individually.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthddi/ns-bthddi-_brb_header">BRB_HEADER</a>



<a href="https://docs.microsoft.com/previous-versions/ff536622(v=vs.85)">BRB_SCO_CLOSE_CHANNEL</a>
 

 

