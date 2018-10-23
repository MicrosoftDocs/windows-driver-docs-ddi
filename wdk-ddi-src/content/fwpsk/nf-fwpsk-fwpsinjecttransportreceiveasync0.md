---
UID: NF:fwpsk.FwpsInjectTransportReceiveAsync0
title: FwpsInjectTransportReceiveAsync0 function
author: windows-driver-content
description: The FwpsInjectTransportReceiveAsync0 function injects packet data from the transport, datagram data, or ICMP error layers into the receive data path.Note  FwpsInjectTransportReceiveAsync0 is a specific version of FwpsInjectTransportReceiveAsync.
old-location: netvista\fwpsinjecttransportreceiveasync0.htm
tech.root: netvista
ms.assetid: 0809a013-9977-44fc-b800-576b4fd983e8
ms.date: 05/02/2018
ms.keywords: FwpsInjectTransportReceiveAsync0, FwpsInjectTransportReceiveAsync0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectTransportReceiveAsync0, netvista.fwpsinjecttransportreceiveasync0, wfp_ref_2_funct_3_fwps_I_2d92a340-1ab7-4eb2-b0c4-47ce8de3daa4.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsInjectTransportReceiveAsync0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsInjectTransportReceiveAsync0 function


## -description


The 
  <b>FwpsInjectTransportReceiveAsync0</b> function injects packet data from the transport, datagram data, or
  ICMP error layers into the receive data path.
<div class="alert"><b>Note</b>  <b>FwpsInjectTransportReceiveAsync0</b> is a specific version of <b>FwpsInjectTransportReceiveAsync</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param injectionHandle [in]

An injection handle that was previously created by a call to the 
     <a href="https://msdn.microsoft.com/61cee8ef-1070-46d4-a541-94a9f09b593b">
     FwpsInjectionHandleCreate0</a> function.


### -param injectionContext [in, optional]

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551202">FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552408">FWPS_PACKET_INJECTION_STATE</a> is
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
     <a href="https://msdn.microsoft.com/fba7eb60-0d19-4bfd-b484-2e615d3e9237">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function. If the 
     <b>compartmentId</b> member is available to callouts, <b>FWPS_METADATA_FIELD_COMPARTMENT_ID</b> will be set in
     the 
     <b>currentMetadataValues</b> member. Otherwise, set this parameter to <b>UNSPECIFIED_COMPARTMENT_ID</b>.


### -param interfaceIndex [in]

The index of the interface on which the original packet data was received. A callout driver should
     use the value of the interface index that is passed as one of the incoming data values to its 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function for this
     parameter if the packet is to be injected into the same interface where the original packet was
     indicated.


### -param subInterfaceIndex [in]

The index of the subinterface on which the original packet data was received. A callout driver
     should use the value of the subinterface index that is passed as one of the incoming data values to its 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function for this
     parameter if the packet is to be injected into the same subinterface where the original packet was
     indicated.


### -param netBufferList [in, out]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a <b>NET_BUFFER_LIST</b> structure to use to
     inject packet data by calling either the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551134">FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff551135">FwpsAllocateNetBufferAndNetBufferList0</a> function. The <b>NET_BUFFER_LIST</b> structure must begin with an
     IP header.


### -param completionFn [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/c03656ec-f0fe-49f5-8a04-2d26ef23c50a">completionFn</a> callout function provided by
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
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure will indicate
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
    <a href="https://msdn.microsoft.com/badb7e91-1d5f-42c3-973b-c7d756d24a01">
    FwpsConstructIpHeaderForTransportPacket0</a> function to correct the IP and upper-level protocol (TCP,
    UDP, and ICMP) checksums. The 
    <i>headerIncludeHeaderSize</i> parameter of 
    <b>FwpsConstructIpHeaderForTransportPacket0</b> should be the same value as the 
    <b>ipHeaderSize</b> member of the 
    <a href="https://msdn.microsoft.com/fba7eb60-0d19-4bfd-b484-2e615d3e9237">
    FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the <i>inMetaValues</i> parameter of the
    callout driver's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function.

If the return value is not <b>STATUS_SUCCESS</b>, the completion function will not be called. In this case,
    the net buffer list pointed to by 
    <i>netBufferList</i> must be freed by a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551172">FwpsFreeNetBufferList0</a> or 
    <a href="https://msdn.microsoft.com/0d0dea63-de0d-4421-b123-ce31ac6af1d9">
    FwpsFreeCloneNetBufferList0</a>.

If the original inbound packet data had been subject to IPsec policy enforcement when it was
    originally processed by the transport layer, the cloned packet injected by this function will bypass
    IPsec verification when it reenters the network stack. Locally generated inbound packets that use the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551135">FwpsAllocateNetBufferAndNetBufferList0</a> function also bypass IPsec verification.

To allow IPsec to process inbound packets first, the callout that inspects the transport layer data
    must have a lower value of 
    <b>subLayerWeight</b> in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552387">FWPS_FILTER0</a> structure than the universal
    sublayer. In addition, the callout driver must not intercept tunnel-mode packets for which the
    combination of 
    <a href="https://msdn.microsoft.com/ac5994a7-411c-47f2-ba1d-2d49c727de8d">
    FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</a> members (
    <b>isTunnelMode</b> &amp;&amp; !
    <b>isDeTunneled</b> ) is returned by the 
    <a href="https://msdn.microsoft.com/c3391615-963b-4916-9280-ce782269692c">
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551199">FwpsPendOperation0</a> and has completed
    with a call to 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551152">FwpsCompleteOperation0</a>:

<b>FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V4</b>

<b>FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V6</b>

A net buffer list to be injected must be passed to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551152">FwpsCompleteOperation0</a> function as the 
    <i>netBufferList</i> argument.

The injected packet can be indicated to the callout driver again. To prevent infinite looping, the
    driver should first call the 
    <a href="https://msdn.microsoft.com/785d99a5-a8c9-4763-bdd4-e26f604f6be7">
    FwpsQueryPacketInjectionState0</a> function before proceeding with a call to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function, and the driver
    should permit packets that have the injection state 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff552408">FWPS_PACKET_INJECTION_STATE</a> set to
    <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b> to pass through unaltered.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552387">FWPS_FILTER0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552391">FWPS_FILTER_CONDITION0</a>



<a href="https://msdn.microsoft.com/fba7eb60-0d19-4bfd-b484-2e615d3e9237">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552408">FWPS_PACKET_INJECTION_STATE</a>



<a href="https://msdn.microsoft.com/ac5994a7-411c-47f2-ba1d-2d49c727de8d">
   FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</a>



<a href="https://msdn.microsoft.com/72759748-fac6-45b9-9a81-ab71e6e7c3ef">
   FwpsAllocateCloneNetBufferList0</a>



<a href="https://msdn.microsoft.com/d7f2d3c0-f2c9-4624-b3e1-9fbbf64c7186">
   FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551152">FwpsCompleteOperation0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551170">FwpsFreeCloneNetBufferList0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551172">FwpsFreeNetBufferList0</a>



<a href="https://msdn.microsoft.com/c3391615-963b-4916-9280-ce782269692c">
   FwpsGetPacketListSecurityInformation0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551185">FwpsInjectNetworkSendAsync0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551180">FwpsInjectionHandleCreate0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551181">FwpsInjectionHandleDestroy0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551199">FwpsPendOperation0</a>



<a href="https://msdn.microsoft.com/785d99a5-a8c9-4763-bdd4-e26f604f6be7">
   FwpsQueryPacketInjectionState0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>



<a href="https://msdn.microsoft.com/c03656ec-f0fe-49f5-8a04-2d26ef23c50a">completionFn</a>
 

 

