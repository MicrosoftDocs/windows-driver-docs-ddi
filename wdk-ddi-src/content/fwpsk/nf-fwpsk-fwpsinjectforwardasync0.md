---
UID: NF:fwpsk.FwpsInjectForwardAsync0
title: FwpsInjectForwardAsync0 function (fwpsk.h)
description: The FwpsInjectForwardAsync0 function injects packet data into the forwarding data path.Note  FwpsInjectForwardAsync0 is a specific version of FwpsInjectForwardAsync.
old-location: netvista\fwpsinjectforwardasync0.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FwpsInjectForwardAsync0 function"]
ms.keywords: FwpsInjectForwardAsync0, FwpsInjectForwardAsync0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectForwardAsync0, netvista.fwpsinjectforwardasync0, wfp_ref_2_funct_3_fwps_I_3aa5a7a1-da9d-478e-b8fe-0effc99a1fa5.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FwpsInjectForwardAsync0
 - fwpsk/FwpsInjectForwardAsync0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - fwpkclnt.lib
 - fwpkclnt.dll
api_name:
 - FwpsInjectForwardAsync0
---

# FwpsInjectForwardAsync0 function


## -description

The 
  <b>FwpsInjectForwardAsync0</b> function injects packet data into the forwarding data path.
<div class="alert"><b>Note</b>  <b>FwpsInjectForwardAsync0</b> is a specific version of <b>FwpsInjectForwardAsync</b>. See <a href="/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters

### -param injectionHandle 

[in]
An injection handle that was previously created by a call to the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">
     FwpsInjectionHandleCreate0</a> function.

### -param injectionContext 

[in, optional]
An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">
     FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.

### -param flags 

[in]
Reserved. Callout drivers must set this parameter to zero.

### -param addressFamily 

[in]
One of the following address families:
     





#### AF_INET

The IPv4 address family.



#### AF_INET6

The IPv6 address family.

### -param compartmentId 

[in]
The identifier of the routing compartment into which the packet data is injected, specified as a 
     <a href="/windows/win32/api/winnt/ne-winnt-compartment_id">COMPARTMENT_ID</a> type. This identifier is provided
     to a callout through the 
     <b>compartmentId</b> member of the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function. If the 
     <b>compartmentId</b> member is available to callouts, FWPS_METADATA_FIELD_COMPARTMENT_ID will be set in
     the 
     <b>currentMetadataValues</b> member. Otherwise, set this parameter to UNSPECIFIED_COMPARTMENT_ID.

### -param interfaceIndex 

[in]
The index of the destination interface (on which the packet data is to be sent). The index is a
     32-bit value. A callout driver should use the value of the interface index that is passed as one of the
     incoming data values to its 
     <a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> callout function for this
     parameter if the packet is to be injected into the same interface where the original packet was
     indicated.

### -param netBufferList 

[in, out]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a NET_BUFFER_LIST structure to inject
     packet data by calling either the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
     FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
     FwpsAllocateNetBufferAndNetBufferList0</a> function. The NET_BUFFER_LIST structure must begin with an
     IP header.

### -param completionFn 

[in]
A pointer to a 
     <a href="/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferList</i> parameter, has been injected into the network stack.

### -param completionContext 

[in, optional]
A pointer to a callout driver-provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.

## -returns

The 
     <b>FwpsInjectForwardAsync0</b> function returns one of the following NTSTATUS codes.

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
       when an error occurred subsequently, in which case the 
       <b>Status</b> member of the completed 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure will indicate
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
    <b>FwpsInjectForwardAsync0</b> function to inject packet data or a packet fragment into the forwarding
    data path.

This function can execute asynchronously. Callout drivers normally inject data into the network stack
    when modifying packet data. For more information about how a callout driver can modify packet data, see 
    <a href="/windows-hardware/drivers/network/callout-driver-operations">Callout Driver Operations</a>.

A packet or packet fragment injected with this function will not be indicated to any WFP layer for
    filtering.

If the return value is not STATUS_SUCCESS, the completion function will not be called. In this case,
    the net buffer list pointed to by 
    <i>netBufferList</i> must be freed by a call to 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a> or 
    <a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">
    FwpsFreeCloneNetBufferList0</a>.

IP packets or fragments can be cloned, modified, and injected back into the network stack. However, a
    fragment group must be reassembled by the callout driver as a single NET_BUFFER_LIST before it can be
    reinjected.

Forward-injected packets do not reenter the forwarding layer. Therefore, they will not be
    reclassified.

## -see-also

<a href="/windows-hardware/drivers/ddi/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
   FwpsAllocateCloneNetBufferList0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
   FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandledestroy0">FwpsInjectionHandleDestroy0</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/network/packet-injection-functions">Packet Injection Functions</a>



<a href="/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>



<a href="/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a>
