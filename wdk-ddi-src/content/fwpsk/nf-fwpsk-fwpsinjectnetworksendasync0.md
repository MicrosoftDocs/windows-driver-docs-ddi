---
UID: NF:fwpsk.FwpsInjectNetworkSendAsync0
title: FwpsInjectNetworkSendAsync0 function (fwpsk.h)
description: The FwpsInjectNetworkSendAsync0 function injects packet data into the send data path.Note  FwpsInjectNetworkSendAsync0 is a specific version of FwpsInjectNetworkSendAsync.
old-location: netvista\fwpsinjectnetworksendasync0.htm
tech.root: netvista
ms.assetid: 9cc76bf7-a744-46f9-89d5-5277744221e5
ms.date: 05/02/2018
ms.keywords: FwpsInjectNetworkSendAsync0, FwpsInjectNetworkSendAsync0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectNetworkSendAsync0, netvista.fwpsinjectnetworksendasync0, wfp_ref_2_funct_3_fwps_I_33cd70a5-56b6-4cb7-bebf-621e180aaa9b.xml
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- fwpkclnt.lib
- fwpkclnt.dll
api_name:
- FwpsInjectNetworkSendAsync0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsInjectNetworkSendAsync0 function


## -description


The 
  <b>FwpsInjectNetworkSendAsync0</b> function injects packet data into the send data path.
<div class="alert"><b>Note</b>  <b>FwpsInjectNetworkSendAsync0</b> is a specific version of <b>FwpsInjectNetworkSendAsync</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param injectionHandle [in]

An injection handle that was previously created by a call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a> function with the 
     <i>flags</i> parameter set to FWPS_INJECTION_TYPE_NETWORK.


### -param injectionContext [in, optional]

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.


### -param flags [in]

Reserved. Callout drivers must set this parameter to zero.


### -param compartmentId [in]

The identifier of the routing compartment into which the packet data is injected, specified as a 
     <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ne-ntdef-compartment_id">COMPARTMENT_ID</a> type. This identifier is provided
     to a callout through the 
     <b>compartmentId</b> member of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
     FWPS_INCOMING_METADATA_VALUES0</a> structure that is passed to the callout driver's 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a> callout function. If the 
     <b>compartmentId</b> member is available to callouts, FWPS_METADATA_FIELD_COMPARTMENT_ID will be set in
     the 
     <b>currentMetadataValues</b> member. Otherwise, set this parameter to UNSPECIFIED_COMPARTMENT_ID.


### -param netBufferList [in, out]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a NET_BUFFER_LIST structure to use to
     inject packet data by calling either the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">FwpsAllocateNetBufferAndNetBufferList0</a> function. The NET_BUFFER_LIST structure must begin with an
     IP header.


### -param completionFn [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>NetBufferList</i> parameter, has been injected into the network stack.


### -param completionContext [in, optional]

A pointer to a callout driver-provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## -returns



The 
     <b>FwpsInjectNetworkSendAsync0</b> function returns one of the following NTSTATUS codes.

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
       <b>Status</b> member of the completed NET_BUFFER_LIST structure will indicate the reason for
       failure.

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
<dt><b>STATUS_FWP_INJECT_HANDLE_STALE</b></dt>
</dl>
</td>
<td width="60%">
The injection handle was not created with the 
       <i>Flags</i> parameter of the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">
       FwpsInjectionHandleCreate0</a> function set to FWPS_INJECTION_TYPE_NETWORK.

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
    <b>FwpsInjectNetworkSendAsync0</b> function to inject network packet data into the send data path. This
    function can execute asynchronously. Callout drivers normally inject data into the network stack when
    modifying packet data. For more information about how a callout driver can modify packet data, see 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/callout-driver-operations">Callout Driver Operations</a>.

If the return value is not STATUS_SUCCESS, the completion function will not be called. In this case,
    the net buffer list pointed to by 
    <i>netBufferList</i> needs to be freed by a call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a> or 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">
    FwpsFreeCloneNetBufferList0</a> functions.

The injected packet can be indicated to the callout driver again. To prevent infinite looping, the
    driver should first call the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">
    FwpsQueryPacketInjectionState0</a> function before proceeding with a call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a> callout function, and the driver
    should permit packets that have the injection state 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> set to
    <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/ns-fwpsk-fwps_incoming_metadata_values0_">
   FWPS_INCOMING_METADATA_VALUES0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
   FwpsAllocateCloneNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
   FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsfreeclonenetbufferlist0">FwpsFreeCloneNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsfreenetbufferlist0">FwpsFreeNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsinjectionhandledestroy0">FwpsInjectionHandleDestroy0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">
   FwpsQueryPacketInjectionState0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a>
 

 

