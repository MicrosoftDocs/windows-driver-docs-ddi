---
UID: NS:wsk._WSK_BUF
title: _WSK_BUF (wsk.h)
description: The WSK_BUF structure defines a data buffer that is used for sending and receiving data over a socket.
old-location: netvista\wsk_buf.htm
tech.root: netvista
ms.assetid: bef653d3-5de3-4af3-8c1f-cff55619e2e9
ms.date: 05/02/2018
keywords: ["_WSK_BUF structure"]
ms.keywords: "*PWSK_BUF, PWSK_BUF, PWSK_BUF structure pointer [Network Drivers Starting with Windows Vista], WSK_BUF, WSK_BUF structure [Network Drivers Starting with Windows Vista], _WSK_BUF, netvista.wsk_buf, wsk/PWSK_BUF, wsk/WSK_BUF, wskref_38d35e0c-e08d-4be7-b5c8-0559774d5de0.xml"
f1_keywords:
 - "wsk/WSK_BUF"
 - "WSK_BUF"
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
- wsk.h
api_name:
- WSK_BUF
product:
- Windows
targetos: Windows
req.typenames: WSK_BUF, *PWSK_BUF
---

# _WSK_BUF structure


## -description


The WSK_BUF structure defines a data buffer that is used for sending and receiving data over a
  socket.


## -struct-fields




### -field Mdl

A pointer to a memory descriptor list (MDL). The MDL can be a single MDL or the first MDL in an
     MDL chain. If the 
     <b>Length</b> member is zero, this pointer can be <b>NULL</b>.


### -field Offset

An offset to where the data starts in the MDL. If the 
     <b>Mdl</b> member points to the first MDL in an MDL chain, this offset must be within the memory buffer
     that is described by the first MDL in the chain. If the 
     <b>Mdl</b> member is <b>NULL</b>, the 
     <b>Offset</b> member is not used.


### -field Length

When a WSK_BUF structure is used to describe a buffer of data to be sent over a socket, this
     member specifies the number of bytes of data in the MDL (or MDL chain) to be sent.
     

When a WSK_BUF structure is used to describe a buffer for receiving data from a socket, this member
     specifies the maximum number of bytes to be received into the MDL (or MDL chain).

When a WSK_BUF structure is contained within either a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_data_indication">WSK_DATA_INDICATION</a> structure or a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_datagram_indication">WSK_DATAGRAM_INDICATION</a> structure,
     this member specifies the number of bytes of received data in the MDL (or MDL chain).


## -remarks



Each MDL in the MDL chain that is pointed to by the 
    <b>Mdl</b> member describes memory that is either locked or from non-paged pool.

When a WSK application passes a pointer to a WSK_BUF structure to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive">WskReceive</a> function, the application can
    specify zero for the 
    <b>Length</b> member of the structure. In that situation, the 
    <b>Mdl</b> member can be <b>NULL</b> because no data will be copied into the buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_datagram_indication">WSK_DATAGRAM_INDICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/ns-wsk-_wsk_data_indication">WSK_DATA_INDICATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_disconnect">WskDisconnect</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive">WskReceive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_receive_from">WskReceiveFrom</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_send">WskSend</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wsk/nc-wsk-pfn_wsk_send_to">WskSendTo</a>
 

 

