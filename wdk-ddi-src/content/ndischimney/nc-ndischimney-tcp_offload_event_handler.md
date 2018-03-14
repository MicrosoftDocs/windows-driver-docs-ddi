---
UID: NC:ndischimney.TCP_OFFLOAD_EVENT_HANDLER
title: TCP_OFFLOAD_EVENT_HANDLER
author: windows-driver-content
description: NDIS calls a protocol driver's or intermediate driver's ProtocolIndicateOffloadEvent function to post an indication that was initiated by an underlying driver's or offload target's call to the NdisTcpOffloadEventHandler function.
old-location: netvista\protocoltcpoffloadevent.htm
old-project: netvista
ms.assetid: b64c0f9e-aa3d-43c5-bdf5-c40cae3929e3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ProtocolTcpOffloadEvent, ProtocolTcpOffloadEvent callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_EVENT_HANDLER, ndischimney/ProtocolTcpOffloadEvent, netvista.protocoltcpoffloadevent, tcp_chim_protocol_func_8cc440e3-7686-42dc-8fff-baf397394951.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	ProtocolTcpOffloadEvent
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# TCP_OFFLOAD_EVENT_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolIndicateOffloadEvent</i> function to post an indication that was initiated by an underlying
  driver's or offload target's call to the 
  <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">
  NdisTcpOffloadEventHandler</a> function.


## -prototype


````
TCP_OFFLOAD_EVENT_HANDLER ProtocolTcpOffloadEvent;

VOID ProtocolTcpOffloadEvent(
  _In_ PVOID OffloadContext,
  _In_ ULONG EventType,
  _In_ ULONG EventSpecificInformation
)
{ ... }
````


## -parameters




### -param OffloadContext [in]

A pointer to the protocol or intermediate driver's 
     <a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a> structure for the
     TCP connection on which the indication is being made. The protocol or intermediate driver supplied this
     pointer as an input parameter to the 
     <a href="..\ndischimney\nf-ndischimney-ndisinitiateoffload.md">NdisInitiateOffload</a> function when
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
       <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">
       NdisTcpOffloadEventHandler</a>.



#### TcpIndicateAbort

Not meaningful.



#### TcpIndicateSendBacklogChange

Specifies the optimum number of send data bytes that the host stack should have outstanding at
       the offload target in order to achieve the best data throughput.


## -returns



None




## -remarks



To propagate the indication to the overlying driver or host stack, the intermediate driver calls the 
    <b>NdisTcpOffloadEventHandler</b> function. The intermediate driver passes the following parameters to the
    
    <b>NdisTcpOffloadEventHandler</b> function:

<ul>
<li>
The 
      <b>NdisOffloadHandle</b> that the offload target stored in its context for the offloaded TCP connection.
      For more information, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
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

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">NdisTcpOffloadEventHandler</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_EVENT_HANDLER callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

