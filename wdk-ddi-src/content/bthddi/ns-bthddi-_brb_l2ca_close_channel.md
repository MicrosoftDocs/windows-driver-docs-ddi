---
UID: NS:bthddi._BRB_L2CA_CLOSE_CHANNEL
title: "_BRB_L2CA_CLOSE_CHANNEL"
author: windows-driver-content
description: The _BRB_L2CA_CLOSE_CHANNEL structure describes an open L2CAP channel to close.
old-location: bltooth\_brb_l2ca_close_channel.htm
old-project: bltooth
ms.assetid: 0a9f3720-8ae4-4219-a8b3-f1b88126f176
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bth_structs_97d7dc1f-eb95-4cf3-8d21-a814622a0b81.xml, bthddi/_BRB_L2CA_CLOSE_CHANNEL, bltooth._brb_l2ca_close_channel, _BRB_L2CA_CLOSE_CHANNEL structure [Bluetooth Devices], _BRB_L2CA_CLOSE_CHANNEL
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bthddi.h
apiname:
-	_BRB_L2CA_CLOSE_CHANNEL
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_CLOSE_CHANNEL structure


## -description


The _BRB_L2CA_CLOSE_CHANNEL structure describes an open L2CAP channel to close.


## -syntax


````
struct _BRB_L2CA_CLOSE_CHANNEL {
  BRB_HEADER           Hdr;
  BTH_ADDR             BtAddress;
  L2CAP_CHANNEL_HANDLE ChannelHandle;
};
````


## -struct-fields




### -field Hdr

A 
     <a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the remote device.


### -field ChannelHandle

The L2CAP channel handle that was returned by Bluetooth driver stack in response to an earlier 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a> or 
     <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536616">
     BRB_L2CA_OPEN_CHANNEL_RESPONSE</a> request. This is the channel handle to close.


## -remarks



To close a L2CAP channel, profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536614">BRB_L2CA_CLOSE_CHANNEL</a> request.

A <b>BRB_L2CA_CLOSE_CHANNEL</b> request can be made for a channel that was initiated locally or remotely. If
    a profile driver has multiple L2CAP channels to a single remote device, it must close each one
    individually.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536615">BRB_L2CA_OPEN_CHANNEL</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536614">BRB_L2CA_CLOSE_CHANNEL</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff536616">
   BRB_L2CA_OPEN_CHANNEL_RESPONSE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20_BRB_L2CA_CLOSE_CHANNEL structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

