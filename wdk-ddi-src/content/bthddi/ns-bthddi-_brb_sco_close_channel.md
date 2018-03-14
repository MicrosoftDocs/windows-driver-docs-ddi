---
UID: NS:bthddi._BRB_SCO_CLOSE_CHANNEL
title: "_BRB_SCO_CLOSE_CHANNEL"
author: windows-driver-content
description: The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close.
old-location: bltooth\_brb_sco_close_channel.htm
old-project: bltooth
ms.assetid: 1921cee1-411b-4fec-acfd-3380e84823b8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_BRB_SCO_CLOSE_CHANNEL, _BRB_SCO_CLOSE_CHANNEL structure [Bluetooth Devices], bltooth._brb_sco_close_channel, bth_structs_d031efa4-0a68-47c0-8344-e95c677661c9.xml, bthddi/_BRB_SCO_CLOSE_CHANNEL"
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
-	_BRB_SCO_CLOSE_CHANNEL
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_CLOSE_CHANNEL structure


## -description


The _BRB_SCO_CLOSE_CHANNEL structure describes a currently open SCO channel to close.


## -syntax


````
struct _BRB_SCO_CLOSE_CHANNEL {
  BRB_HEADER         Hdr;
  BTH_ADDR           BtAddress;
  SCO_CHANNEL_HANDLE ChannelHandle;
};
````


## -struct-fields




### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The Bluetooth address of the remote device.


### -field ChannelHandle

The handle to the SCO channel to close.


## -remarks



To close a SCO channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536622">BRB_SCO_CLOSE_CHANNEL</a> request.

A <b>BRB_SCO_CLOSE_CHANNEL</b> request can be made for a channel that was initiated locally or remotely. If a
    profile driver has multiple SCO connections to a single remote device, it must close each one
    individually.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536622">BRB_SCO_CLOSE_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



 

 


