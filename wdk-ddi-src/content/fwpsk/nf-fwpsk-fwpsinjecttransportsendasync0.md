---
UID: NF:fwpsk.FwpsInjectTransportSendAsync0
title: FwpsInjectTransportSendAsync0 function (fwpsk.h)
description: The FwpsInjectTransportSendAsync0 function injects packet data from the transport, datagram data, or ICMP error layers into the send data path.Note  FwpsInjectTransportSendAsync0 is the specific version of FwpsInjectTransportSendAsync used in Windows Vista and later. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information. For Windows 7, FwpsInjectTransportSendAsync1 is available.
old-location: netvista\fwpsinjecttransportsendasync0.htm
tech.root: netvista
ms.assetid: 1298a825-16c4-49ab-b038-19247975ea46
ms.date: 05/02/2018
ms.keywords: FwpsInjectTransportSendAsync0, FwpsInjectTransportSendAsync0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectTransportSendAsync0, netvista.fwpsinjecttransportsendasync0, wfp_ref_2_funct_3_fwps_I_76082863-1d74-4916-9766-c65b745dca60.xml
f1_keywords:
 - "fwpsk/FwpsInjectTransportSendAsync0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsInjectTransportSendAsync0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsInjectTransportSendAsync0 function


## -description


The 
  <b>FwpsInjectTransportSendAsync0</b> function injects packet data from the transport, datagram data, or ICMP
  error layers into the send data path.
<div class="alert"><b>Note</b>  <b>FwpsInjectTransportSendAsync0</b> is the specific version of <b>FwpsInjectTransportSendAsync</b> used in Windows Vista and later. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information. For Windows 7, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjecttransportsendasync1">FwpsInjectTransportSendAsync1</a> is available.</div><div> </div>

## -parameters




### -param injectionHandle [in]

An injection handle that was previously created by a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">
     FwpsInjectionHandleCreate0</a> function.


### -param injectionContext [in, optional]

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.


### -param endpointHandle [in]

A handle that indicates the stack transport endpoint in the send data path into which the packet
     is to be injected. This endpoint handle is provided to a callout through the 
     <b>transportEndpointHandle</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function. Callout
     drivers should use the provided handle to inject cloned packets back into the data path as soon as
     possible, before the socket associated with the stack endpoint is closed and the handle becomes no
     longer valid.


### -param flags [in]

Reserved. Callout drivers must set this parameter to zero.


### -param sendArgs [in, optional]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_transport_send_params0_">
     FWPS_TRANSPORT_SEND_PARAMS0</a> structure that specifies the properties of the current outbound
     packet. Can be <b>NULL</b> only if the net buffer list to be injected contains an IP header (for example, if
     the packet is sent via a raw socket).


### -param addressFamily [in]

One of the following address families:
     





#### AF_INET

The IPv4 address family.



#### AF_INET6

The IPv6 address family.


### -param compartmentId [in]

The identifier of the routing compartment into which the packet data is injected, specified as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ne-ntdef-compartment_id">COMPARTMENT_ID</a> type. This identifier is provided
     to a callout through the 
     <b>compartmentId</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function. If the 
     <b>compartmentId</b> member is available to callouts, FWPS_METADATA_FIELD_COMPARTMENT_ID will be set in
     the 
     <b>currentMetadataValues</b> member. Otherwise, set this parameter to UNSPECIFIED_COMPARTMENT_ID.


### -param netBufferList [in, out]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a <b>NET_BUFFER_LIST</b> structure to use to
     inject packet data by calling either the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
     FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
     FwpsAllocateNetBufferAndNetBufferList0</a> function.


### -param completionFn [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferList</i> parameter, has been injected into the network stack.


### -param completionContext [in, optional]

A pointer to a callout driver-provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## -returns



The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectnetworksendasync0">FwpsInjectNetworkSendAsync0</a> function returns one of the following NTSTATUS codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The packet data injection was initiated successfully. The filter engine will call the completion
       function after the filter engine has completed injecting the packet data into the network stack, or
       when an error occurred subsequently. In case of an error, the 
       <b>Status</b> member of the completed 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure will indicate
       the reason for failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_TCPIP_NOT_READY</b></dt>
</dl>
</td>
<td width="60%">
The TCP/IP network stack is not ready to accept injection of packet data.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FWP_INJECT_HANDLE_CLOSING</b></dt>
</dl>
</td>
<td width="60%">
The injection handle is being closed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A callout driver calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectnetworksendasync0">FwpsInjectNetworkSendAsync0</a> function to inject packet data from the transport, datagram data, or
    ICMP error layers into the send data path. At these layers, the IP header might not yet be formed, and
    when IPsec policy is active, the packet data is not encrypted or signed. Therefore, this function is
    ideal to use for packet inspection in an IPsec-enabled environment.

This function can execute asynchronously.

If the return value is not STATUS_SUCCESS, the completion function will not be called. In this case,
    the net buffer list pointed to by 
    <i>netBufferList</i> needs to be freed by a call to 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a>.

Callout drivers normally inject data into the network stack when they modify packet data. For more
    information about how a callout driver can modify packet data, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/callout-driver-operations">Callout Driver Operations</a>.

Due to the TCP protocol locking semantics, TCP can only be injected Out of Band at any transport layer or equivalent layer, so FwpsInjectTransportReceiveAsync0 and FwpsInjectTransportSendAsync0 must be queued and run by a DPC.

The injected packet can be indicated to the callout driver again. To prevent infinite looping, the
    driver should first call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a> function before calling the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function, and permit
    packets that have the injection state 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> set to
    <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.

The 
    <i>endpointHandle</i> parameter, as well as members declared in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_transport_send_params0_">
    FWPS_TRANSPORT_SEND_PARAMS0</a> structure pointed to by the 
    <i>sendArgs</i> parameter, are provided to callouts from the following network layers:


<dl>
<dd>
FWPS_LAYER_OUTBOUND_TRANSPORT_V4

</dd>
<dd>
FWPS_LAYER_OUTBOUND_TRANSPORT_V6

</dd>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V4 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)

</dd>
<dd>
FWPS_LAYER_DATAGRAM_DATA_V6 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)

</dd>
<dd>
FWPS_LAYER_OUTBOUND_ICMP_ERROR_V4

</dd>
<dd>
FWPS_LAYER_OUTBOUND_ICMP_ERROR_V6

</dd>
</dl>


The datagram belongs to a raw socket if both of the following are true: <ul>
<li>The <b>currentMetadataValues</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a> structure has the <b>FWPS_METADATA_FIELD_IP_HEADER_SIZE</b> flag set.</li>
<li>The <b>ipHeaderSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">FWPS_INCOMING_METADATA_VALUES0</a> structure is greater than zero.</li>
</ul>


At the following network layers, if the datagram belongs to a raw socket, the net buffer list pointed to by <i>netBufferList</i> must be adjusted to start at the IP header (which must be prepended to the net buffer list):<ul>
<li>
FWPS_LAYER_DATAGRAM_DATA_V4 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)

</li>
<li>
FWPS_LAYER_DATAGRAM_DATA_V6 (when outbound direction is specified with FWP_DIRECTION_OUTBOUND)

</li>
</ul>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_transport_send_params0_">FWPS_TRANSPORT_SEND_PARAMS0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
   FwpsAllocateCloneNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
   FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjecttransportsendasync1">FwpsInjectTransportSendAsync1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandledestroy0">FwpsInjectionHandleDestroy0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">
   FwpsQueryPacketInjectionState0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a>
 

 

