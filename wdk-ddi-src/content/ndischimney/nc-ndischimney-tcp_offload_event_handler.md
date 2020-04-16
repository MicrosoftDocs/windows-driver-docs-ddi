---
UID: NC:ndischimney.TCP_OFFLOAD_EVENT_HANDLER
title: TCP_OFFLOAD_EVENT_HANDLER (ndischimney.h)
description: NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisTcpOffloadEventHandler function.
old-location: netvista\protocoltcpoffloadevent.htm
tech.root: netvista
ms.assetid: b64c0f9e-aa3d-43c5-bdf5-c40cae3929e3
ms.date: 05/02/2018
keywords: ["TCP_OFFLOAD_EVENT_HANDLER callback function"]
ms.keywords: ProtocolTcpOffloadEvent, ProtocolTcpOffloadEvent callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_EVENT_HANDLER, TCP_OFFLOAD_EVENT_HANDLER callback, ndischimney/ProtocolTcpOffloadEvent, netvista.protocoltcpoffloadevent, tcp_chim_protocol_func_8cc440e3-7686-42dc-8fff-baf397394951.xml
f1_keywords:
 - "ndischimney/ProtocolTcpOffloadEvent"
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- UserDefined
api_location:
- Ndischimney.h
api_name:
- ProtocolTcpOffloadEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# TCP_OFFLOAD_EVENT_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolIndicateOffloadEvent</i> function to post an indication that was initiated by an underlying
  driver's or offload target's call to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">
  NdisTcpOffloadEventHandler</a> function.


## -parameters




### -param OffloadContext [in]

A pointer to the protocol or intermediate driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_offload_handle">NDIS_OFFLOAD_HANDLE</a> structure for the
     TCP connection on which the indication is being made. The protocol or intermediate driver supplied this
     pointer as an input parameter to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisinitiateoffload">NdisInitiateOffload</a> function when
     offloading the connection.


### -param EventType [in]

The event being indicated as one of the following TCP_OFFLOAD_EVENT_TYPE values:
     





#### TcpIndicateDisconnect

Indicates that the remote host initiated a graceful disconnect by sending a FIN segment on the
       connection.



#### TcpIndicateRetrieve

Indicates that the offload target is requesting the host stack to terminate the offload of a TCP
       connection.



#### TcpIndicateAbort

Indicates that the remote host initiated an abortive disconnect by sending an acceptable RST
       segment on the connection.



#### TcpIndicateSendBacklogChange

Indicates a change in the preferred send backlog size.


### -param EventSpecificInformation [in]

Specifies additional information about the event being indicated as follows:
     





#### TcpIndicateDisconnect

Not meaningful.



#### TcpIndicateRetrieve

Indicates the reason for the upload request as a TCP_UPLOAD_REASON value. For more information,
       see 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">
       NdisTcpOffloadEventHandler</a>.



#### TcpIndicateAbort

Not meaningful.



#### TcpIndicateSendBacklogChange

Specifies the optimum number of send data bytes that the host stack should have outstanding at
       the offload target in order to achieve the best data throughput.


## -remarks



To propagate the indication to the overlying driver or host stack, the intermediate driver calls the 
    <b>NdisTcpOffloadEventHandler</b> function. The intermediate driver passes the following parameters to the    
    <b>NdisTcpOffloadEventHandler</b> function:

<ul>
<li>
The 
      <b>NdisOffloadHandle</b> that the offload target stored in its context for the offloaded TCP connection.
      For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The 
      <i>EventType</i> that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadEvent</i> function.

</li>
<li>
The 
      <i>EventSpecificInformation</i> that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadEvent</i> function.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">NdisTcpOffloadEventHandler</a>
 

 

