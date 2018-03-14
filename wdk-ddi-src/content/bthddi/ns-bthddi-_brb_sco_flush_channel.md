---
UID: NS:bthddi._BRB_SCO_FLUSH_CHANNEL
title: "_BRB_SCO_FLUSH_CHANNEL"
author: windows-driver-content
description: The _BRB_SCO_FLUSH_CHANNEL structure describes a flush operation for a SCO channel.
old-location: bltooth\_brb_sco_flush_channel.htm
old-project: bltooth
ms.assetid: 17ee1a71-2aaf-421d-9ae9-019fe0d2f595
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_BRB_SCO_FLUSH_CHANNEL, _BRB_SCO_FLUSH_CHANNEL structure [Bluetooth Devices], bltooth._brb_sco_flush_channel, bth_structs_d2a9941d-7091-402d-87bc-a5da139dfc1f.xml, bthddi/_BRB_SCO_FLUSH_CHANNEL"
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
-	_BRB_SCO_FLUSH_CHANNEL
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_SCO_FLUSH_CHANNEL structure


## -description


The _BRB_SCO_FLUSH_CHANNEL structure describes a flush operation for a SCO channel.


## -syntax


````
struct _BRB_SCO_FLUSH_CHANNEL {
  BRB_HEADER         Hdr;
  BTH_ADDR           BtAddress;
  SCO_CHANNEL_HANDLE ChannelHandle;
  ULONG              FlushFlags;
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

The handle to the SCO channel to flush.


### -field FlushFlags



#####  Valid flags may be combined using a logical OR
     operation:



#### SCO_FLUSH_DIRECTION_OUT



#### SCO_FLUSH_DIRECTION_IN



#### 


## -remarks



To flush a SCO channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536623">BRB_SCO_FLUSH_CHANNEL</a> request.

All pending data transfer IRPs will be completed with STATUS_REQUEST_ABORTED. In-progress IRPs will be
    completed normally, with success or failure, depending on whether the Bluetooth driver stack was able to
    transfer data to or from the remote device.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536623">BRB_SCO_FLUSH_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



 

 


