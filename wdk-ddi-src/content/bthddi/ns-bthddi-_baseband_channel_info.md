---
UID: NS:bthddi._BASEBAND_CHANNEL_INFO
title: "_BASEBAND_CHANNEL_INFO"
author: windows-driver-content
description: The BASEBAND_CHANNEL_INFO structure describes output information about the baseband channel that is used by a SCO link after a BRB_GET_CHANNEL_INFO BRB completes.
old-location: bltooth\baseband_channel_info.htm
old-project: bltooth
ms.assetid: c9328791-898e-48f2-acfd-30c8a36fcd29
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: bth_structs_849b4363-4e7e-4fee-b5c1-86b32431a6dd.xml, *PBASEBAND_CHANNEL_INFO, PBASEBAND_CHANNEL_INFO, _BASEBAND_CHANNEL_INFO, bltooth.baseband_channel_info, bthddi/PBASEBAND_CHANNEL_INFO, BASEBAND_CHANNEL_INFO structure [Bluetooth Devices], PBASEBAND_CHANNEL_INFO structure pointer [Bluetooth Devices], bthddi/BASEBAND_CHANNEL_INFO, BASEBAND_CHANNEL_INFO
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
-	BASEBAND_CHANNEL_INFO
product: Windows
targetos: Windows
req.typenames: BASEBAND_CHANNEL_INFO, *PBASEBAND_CHANNEL_INFO
---

# _BASEBAND_CHANNEL_INFO structure


## -description


The BASEBAND_CHANNEL_INFO structure describes output information about the baseband channel that is
  used by a SCO link after a BRB_GET_CHANNEL_INFO BRB completes.


## -syntax


````
typedef struct _BASEBAND_CHANNEL_INFO {
  UCHAR  Transmission_Interval;
  UCHAR  Retransmission_Window;
  UCHAR  AirMode;
  USHORT Rx_Packet_Length;
  USHORT Tx_Packet_Length;
} BASEBAND_CHANNEL_INFO, *PBASEBAND_CHANNEL_INFO;
````


## -struct-fields




### -field Transmission_Interval

The elapsed time, in slots, between two consecutive SCO instants. This member will return zero for
     SCO links.


### -field Retransmission_Window

The length of time, in slots, that an eSCO channel can use to retransmit a request. This member
     will return zero for SCO links.


### -field AirMode

The air mode data format used by the baseband channel. Possible values include:
     


<dl>
<dt>A-LAW LOG
     </dt>
<dt>CVSD
     </dt>
<dt>MU-LAW LOG
     </dt>
<dt>TRANSPARENT DATA</dt>
</dl>



### -field Rx_Packet_Length

The size, in bytes, of the eSCO payload in the receive direction. This member will return zero for
     SCO links.


### -field Tx_Packet_Length

The size, in bytes, of the eSCO payload in the transmit direction. This member will return zero
     for SCO links.


## -remarks



Profile drivers access the BASEBAND_CHANNEL_INFO structure through the 
    <b>BasebandInfo</b> member of the 
    <a href="..\bthddi\ns-bthddi-_brb_sco_get_channel_info.md">
    _BRB_SCO_GET_CHANNEL_INFO</a> structure.




## -see-also

<a href="..\bthddi\ns-bthddi-_brb_sco_get_channel_info.md">_BRB_SCO_GET_CHANNEL_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BASEBAND_CHANNEL_INFO structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

