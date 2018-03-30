---
UID: NS:bthddi._BRB_L2CA_PING
title: "_BRB_L2CA_PING"
author: windows-driver-content
description: The _BRB_L2CA_PING structure describes a request to ping a remote radio.
old-location: bltooth\_brb_l2ca_ping.htm
old-project: bltooth
ms.assetid: 699d2ea6-3bf3-457c-b05e-c45ec4c71fb6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_BRB_L2CA_PING, _BRB_L2CA_PING structure [Bluetooth Devices], bltooth._brb_l2ca_ping, bth_structs_40384235-0f47-4870-a6be-72e807ee439d.xml, bthddi/_BRB_L2CA_PING"
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
-	_BRB_L2CA_PING
product: Windows
targetos: Windows
req.typenames: 
---

# _BRB_L2CA_PING structure


## -description


The _BRB_L2CA_PING structure describes a request to ping a remote radio.


## -struct-fields




### -field Hdr

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a> structure that contains information
     about the current BRB.


### -field BtAddress

The address of the device that the ping is sent to.


### -field PingRequestLength

The length, in bytes, of the data to send in the ping signal.


### -field PingRequestData

The data to send in the ping signal.


### -field PingResponseLength

The length, in bytes, of the data that the remote device responded to the ping signal with.


### -field PingResponseData

The data that the remote device responded to the ping signal with.


## -remarks



To ping a remote radio, by transmitting a L2CA_EchoReq message and receiving a L2CAP_EchoRsp message,
    profile drivers should 
    <a href="https://msdn.microsoft.com/53a692e7-9c71-4dca-9331-32ac97b94179">build and send</a> a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536617">BRB_L2CA_PING</a> request.

BRB_L2CA_PING is primarily used for debugging.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536617">BRB_L2CA_PING</a>
 

 

