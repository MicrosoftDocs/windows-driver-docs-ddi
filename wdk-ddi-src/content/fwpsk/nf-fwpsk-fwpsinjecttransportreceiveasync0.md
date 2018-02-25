---
UID: NF:fwpsk.FwpsInjectTransportReceiveAsync0
title: FwpsInjectTransportReceiveAsync0 function
author: windows-driver-content
description: The FwpsInjectTransportReceiveAsync0 function injects packet data from the transport, datagram data, or ICMP error layers into the receive data path.Note  FwpsInjectTransportReceiveAsync0 is a specific version of FwpsInjectTransportReceiveAsync.
old-location: netvista\fwpsinjecttransportreceiveasync0.htm
old-project: netvista
ms.assetid: 0809a013-9977-44fc-b800-576b4fd983e8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 0, A, F, FwpsInjectTransportReceiveAsync0, FwpsInjectTransportReceiveAsync0 function [Network Drivers Starting with Windows Vista], I, R, T, a, c, e, fwpsk/FwpsInjectTransportReceiveAsync0, i, j, n, netvista.fwpsinjecttransportreceiveasync0, o, p, r, s, t, v, w, wfp_ref_2_funct_3_fwps_I_2d92a340-1ab7-4eb2-b0c4-47ce8de3daa4.xml, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsInjectTransportReceiveAsync0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsInjectTransportReceiveAsync0 function


## -description


The 
  <b>FwpsInjectTransportReceiveAsync0</b> function injects packet data from the transport, datagram data, or
  ICMP error layers into the receive data path.
<div class="alert"><b>Note</b>  <b>FwpsInjectTransportReceiveAsync0</b> is a specific version of <b>FwpsInjectTransportReceiveAsync</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
NTSTATUS NTAPI FwpsInjectTransportReceiveAsync0(
  _In_       HANDLE                injectionHandle,
  _In_opt_   HANDLE                injectionContext,
  _Reserved_ PVOID                 reserved,
  _In_       UINT32                flags,
  _In_       ADDRESS_FAMILY        addressFamily,
  _In_       COMPARTMENT_ID        compartmentId,
  _In_       IF_INDEX              interfaceIndex,
  _In_       IF_INDEX              subInterfaceIndex,
  _Inout_    NET_BUFFER_LIST       *netBufferList,
  _In_       FWPS_INJECT_COMPLETE0 completionFn,
  _In_opt_   HANDLE                completionContext
);
````


## -parameters




### -param injectionHandle [in]

An injection handle that was previously created by a call to the 
     <a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">
     FwpsInjectionHandleCreate0</a> function.


### -param injectionContext [in, optional]

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.


### -param reserved

Reserved. Callout drivers must set this parameter to zero.


### -param flags [in]

Reserved. Callout drivers must set this parameter to zero.


### -param addressFamily [in]

One of the following address families:
     





#### AF_INET

The IPv4 address family.



#### AF_INET6

The IPv6 address family.


### -param compartmentId [in]

The identifier of the routing compartment into which the packet data is injected, specified as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff542009">COMPARTMENT_ID</a> type. This identifier is provided
     to a callout through the 
     <b>compartmentId</b> member of the 
     <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function. If the 
     <b>compartmentId</b> member is available to callouts, <b>FWPS_METADATA_FIELD_COMPARTMENT_ID</b> will be set in
     the 
     <b>currentMetadataValues</b> member. Otherwise, set this parameter to <b>UNSPECIFIED_COMPARTMENT_ID</b>.


### -param interfaceIndex [in]

The index of the interface on which the original packet data was received. A callout driver should
     use the value of the interface index that is passed as one of the incoming data values to its 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function for this
     parameter if the packet is to be injected into the same interface where the original packet was
     indicated.


### -param subInterfaceIndex [in]

The index of the subinterface on which the original packet data was received. A callout driver
     should use the value of the subinterface index that is passed as one of the incoming data values to its 
     <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function for this
     parameter if the packet is to be injected into the same subinterface where the original packet was
     indicated.


### -param netBufferList [in, out]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a <b>NET_BUFFER_LIST</b> structure to use to
     inject packet data by calling either the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a> function. The <b>NET_BUFFER_LIST</b> structure must begin with an
     IP header.


### -param completionFn [in]

A pointer to a 
     <a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferList</i> parameter, has been injected into the network stack.


### -param completionContext [in, optional]

A pointer to a callout driver–provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## -returns



The 
     <b>FwpsInjectTransportReceiveAsync0</b> function returns one of the following <b>NTSTATUS</b> codes.

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
       <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure will indicate
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
    <b>FwpsInjectTransportReceiveAsync0</b> function to inject packet data from the transport, datagram data,
    or ICMP error layers into the receive data path. This function can execute asynchronously. Callout
    drivers normally inject data into the network stack when modifying packet data. For more information
    about how a callout driver can modify packet data, see 
    <a href="https://msdn.microsoft.com/24940254-c9ed-45f7-8a67-20978a8efd3f">Callout Driver Operations</a>.

If a callout driver modified a packet that it will inject with 
    <b>FwpsInjectTransportReceiveAsync0</b>, it should call the 
    <a href="..\fwpsk\nf-fwpsk-fwpsconstructipheaderfortransportpacket0.md">
    FwpsConstructIpHeaderForTransportPacket0</a> function to correct the IP and upper-level protocol (TCP,
    UDP, and ICMP) checksums. The 
    <i>headerIncludeHeaderSize</i> parameter of 
    <b>FwpsConstructIpHeaderForTransportPacket0</b> should be the same value as the 
    <b>ipHeaderSize</b> member of the 
    <a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
    FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the <i>inMetaValues</i> parameter of the
    callout driver's 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function.

If the return value is not <b>STATUS_SUCCESS</b>, the completion function will not be called. In this case,
    the net buffer list pointed to by 
    <i>netBufferList</i> must be freed by a call to 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">FwpsFreeNetBufferList0</a> or 
    <a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">
    FwpsFreeCloneNetBufferList0</a>.

If the original inbound packet data had been subject to IPsec policy enforcement when it was
    originally processed by the transport layer, the cloned packet injected by this function will bypass
    IPsec verification when it reenters the network stack. Locally generated inbound packets that use the 
    <a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">FwpsAllocateNetBufferAndNetBufferList0</a> function also bypass IPsec verification.

To allow IPsec to process inbound packets first, the callout that inspects the transport layer data
    must have a lower value of 
    <b>subLayerWeight</b> in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552387">FWPS_FILTER0</a> structure than the universal
    sublayer. In addition, the callout driver must not intercept tunnel-mode packets for which the
    combination of 
    <a href="..\fwpsk\ns-fwpsk-fwps_packet_list_inbound_ipsec_information0_.md">
    FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</a> members (
    <b>isTunnelMode</b> &amp;&amp; !
    <b>isDeTunneled</b> ) is returned by the 
    <a href="..\fwpsk\nf-fwpsk-fwpsgetpacketlistsecurityinformation0.md">
    FwpsGetPacketListSecurityInformation0</a> function. The callout driver must wait for the packet to be
    detunneled and then should intercept it at the transport layer or at a forward layer.

This function can be called from one of the following transport layers if the
    <b>FWPS_METADATA_FIELD_ALE_CLASSIFY_REQUIRED</b> metadata flag is not set:

<b>FWPS_LAYER_INBOUND_TRANSPORT_V4</b>

<b>FWPS_LAYER_INBOUND_TRANSPORT_V6</b>

<b>FWPS_LAYER_DATAGRAM_DATA_V4</b> (when inbound direction is specified with <b>FWP_DIRECTION_INBOUND</b>)

<b>FWPS_LAYER_DATAGRAM_DATA_V6</b> (when inbound direction is specified with <b>FWP_DIRECTION_INBOUND</b>)

<b>FWPS_LAYER_INBOUND_ICMP_ERROR_V4</b>

<b>FWPS_LAYER_INBOUND_ICMP_ERROR_V6</b>

Otherwise, this function should be called from the following Application Layer Enforcement (ALE) layers
    after a pended ALE operation was initiated with a call to 
    <a href="..\fwpsk\nf-fwpsk-fwpspendoperation0.md">FwpsPendOperation0</a> and has completed
    with a call to 
    <a href="..\fwpsk\nf-fwpsk-fwpscompleteoperation0.md">FwpsCompleteOperation0</a>:

<b>FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V4</b>

<b>FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V6</b>

A net buffer list to be injected must be passed to the 
    <a href="..\fwpsk\nf-fwpsk-fwpscompleteoperation0.md">FwpsCompleteOperation0</a> function as the 
    <i>netBufferList</i> argument.

The injected packet can be indicated to the callout driver again. To prevent infinite looping, the
    driver should first call the 
    <a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">
    FwpsQueryPacketInjectionState0</a> function before proceeding with a call to the 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> callout function, and the driver
    should permit packets that have the injection state 
    <a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a> set to
    <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b> to pass through unaltered.




## -see-also

<a href="..\fwpsk\nf-fwpsk-fwpsgetpacketlistsecurityinformation0.md">
   FwpsGetPacketListSecurityInformation0</a>



<a href="..\fwpsk\nf-fwpsk-fwpscompleteoperation0.md">FwpsCompleteOperation0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsquerypacketinjectionstate0.md">
   FwpsQueryPacketInjectionState0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsinjectnetworksendasync0.md">FwpsInjectNetworkSendAsync0</a>



<a href="..\fwpsk\ns-fwpsk-fwps_incoming_metadata_values0_.md">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="..\fwpsk\nf-fwpsk-fwpspendoperation0.md">FwpsPendOperation0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0.md">
   FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="..\fwpsk\nc-fwpsk-fwps_inject_complete0.md">completionFn</a>



<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandlecreate0.md">FwpsInjectionHandleCreate0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552391">FWPS_FILTER_CONDITION0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsinjectionhandledestroy0.md">FwpsInjectionHandleDestroy0</a>



<a href="..\fwpsk\ne-fwpsk-fwps_packet_injection_state_.md">FWPS_PACKET_INJECTION_STATE</a>



<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>



<a href="..\fwpsk\nf-fwpsk-fwpsfreenetbufferlist0.md">FwpsFreeNetBufferList0</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552387">FWPS_FILTER0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsfreeclonenetbufferlist0.md">FwpsFreeCloneNetBufferList0</a>



<a href="..\fwpsk\nf-fwpsk-fwpsallocateclonenetbufferlist0.md">
   FwpsAllocateCloneNetBufferList0</a>



<a href="..\fwpsk\ns-fwpsk-fwps_packet_list_inbound_ipsec_information0_.md">
   FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsInjectTransportReceiveAsync0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

