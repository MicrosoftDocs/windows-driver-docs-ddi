---
UID: NS:bthddi._BASEBAND_CHANNEL_INFO
title: "_BASEBAND_CHANNEL_INFO"
author: windows-driver-content
description: The BASEBAND_CHANNEL_INFO structure describes output information about the baseband channel that is used by a SCO link after a BRB_GET_CHANNEL_INFO BRB completes.
old-location: bltooth\baseband_channel_info.htm
old-project: bltooth
ms.assetid: c9328791-898e-48f2-acfd-30c8a36fcd29
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: "*PBASEBAND_CHANNEL_INFO, BASEBAND_CHANNEL_INFO, BASEBAND_CHANNEL_INFO structure [Bluetooth Devices], PBASEBAND_CHANNEL_INFO, PBASEBAND_CHANNEL_INFO structure pointer [Bluetooth Devices], _BASEBAND_CHANNEL_INFO, bltooth.baseband_channel_info, bth_structs_849b4363-4e7e-4fee-b5c1-86b32431a6dd.xml, bthddi/BASEBAND_CHANNEL_INFO, bthddi/PBASEBAND_CHANNEL_INFO"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	BASEBAND_CHANNEL_INFO
product:
- Windows
targetos: Windows
req.typenames: BASEBAND_CHANNEL_INFO, *PBASEBAND_CHANNEL_INFO
---

# _BASEBAND_CHANNEL_INFO structure


## -description


The BASEBAND_CHANNEL_INFO structure describes output information about the baseband channel that is
  used by a SCO link after a BRB_GET_CHANNEL_INFO BRB completes.


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
    <a href="https://msdn.microsoft.com/1a7eb79c-5a3e-4977-ba1f-682bbebb0494">
    _BRB_SCO_GET_CHANNEL_INFO</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536868">_BRB_SCO_GET_CHANNEL_INFO</a>
 

 

