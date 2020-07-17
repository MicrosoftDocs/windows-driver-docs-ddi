---
UID: NF:fwpsk.FwpsInjectMacReceiveAsync0
title: FwpsInjectMacReceiveAsync0 function (fwpsk.h)
description: The FwpsInjectMacReceiveAsync0 function can reinject a previously absorbed media access control (MAC) frame (or a clone of the frame) back to the layer 2 inbound data path it was intercepted from, or inject an invented MAC frame.
old-location: netvista\fwpsinjectmacreceiveasync0.htm
tech.root: netvista
ms.assetid: 8B03835A-98EE-4157-BD05-C52D01EE5F5E
ms.date: 05/02/2018
keywords: ["FwpsInjectMacReceiveAsync0 function"]
ms.keywords: FwpsInjectMacReceiveAsync0, FwpsInjectMacReceiveAsync0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsInjectMacReceiveAsync0, netvista.fwpsinjectmacreceiveasync0
f1_keywords:
 - "fwpsk/FwpsInjectMacSendAsync0"
 - "FwpsInjectMacSendAsync0"
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
- FwpsInjectMacSendAsync0
product:
- Windows
targetos: Windows
req.typenames: 
---

# FwpsInjectMacReceiveAsync0 function


## -description


The <b>FwpsInjectMacReceiveAsync0</b> function can  reinject a previously absorbed media access control (MAC) frame (or a clone of the frame) back to the layer 2 inbound data path from which it was intercepted, or inject an invented MAC frame.<div class="alert"><b>Note</b>  <b>FwpsInjectMacReceiveAsync0</b> is a specific version of <b>FwpsInjectMacReceiveAsync</b>. See <a href="https://docs.microsoft.com/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>



## -parameters




### -param injectionHandle [in]

An injection handle that was previously obtained by a call to  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a> function with the <i>flags</i> parameter set to FWPS_INJECTION_TYPE_L2. 

<div class="alert"><b>Note</b>  Set the <i>addressFamily</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">FwpsInjectionHandleCreate0</a> function to AF_UNSPEC.</div>
<div> </div>

### -param injectionContext [in, optional]

An optional handle to the injection context. If specified, it can be obtained by calling the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">
     FwpsQueryPacketInjectionState0</a> function when the packet injection state 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/ne-fwpsk-fwps_packet_injection_state_">FWPS_PACKET_INJECTION_STATE</a> is
     <b>FWPS_PACKET_INJECTED_BY_SELF</b> or <b>FWPS_PACKET_PREVIOUSLY_INJECTED_BY_SELF</b>.


### -param flags [in]

Reserved. Must be set to zero.


### -param layerId [in]

The run-time identifier for the filtering layer at which the data stream is being processed. 


### -param interfaceIndex [in]

The interface index that is passed to the callout driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> incoming value FWPS_FIELD_<i>Xxx</i>_MAC_FRAME_<i>Xxx</i>_INTERFACE_INDEX.


### -param NdisPortNumber [in]

The NDIS port number  that is passed to the callout driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a> incoming value FWPS_FIELD_<i>Xxx</i>_MAC_FRAME_<i>Xxx</i>_NDIS_PORT.


### -param netBufferLists [in, out]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure that describes
     the packet data that is being injected. A callout driver allocates a NET_BUFFER_LIST structure to use to
     inject packet data by calling either the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">FwpsAllocateCloneNetBufferList0</a> function or the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">FwpsAllocateNetBufferAndNetBufferList0</a> function. 
     
The NET_BUFFER_LIST structure must begin with an IP header if calling this function at the Ethernet layer where `(layerId == FWPS_LAYER_INBOUND_MAC_FRAME_ETHERNET)`.

For receive injection in the native case, where `(layerId == FWPS_LAYER_INBOUND_MAC_FRAME_NATIVE)`, the NET_BUFFER_LIST must begin with a MAC header.

### -param completionFn [in]

A pointer to a 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a> callout function provided by
     the callout driver. The filter engine calls this function after the packet data, described by the 
     <i>netBufferLists</i> parameter, has been injected into the network stack. This pointer must be specified when injecting cloned or created NET_BUFFER_LIST structures. When injecting original  NET_BUFFER_LIST structures, this parameter can be NULL if the original structures  are not altered.


### -param completionContext [in, optional]

A pointer to a callout driver–provided context that is passed to the callout function pointed to
     by the 
     <i>completionFn</i> parameter. This parameter is optional and can be <b>NULL</b>.


## -returns



The 
     <b>FwpsInjectMacReceiveAsync0</b> function returns one of the following NTSTATUS codes.

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
The MAC frame data injection was initiated successfully. The filter engine calls the completion
       function after the filter engine has completed injecting the MAC frame data, or
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
The MAC layer is not ready to accept injection of packet data.

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
       <i>flags</i> parameter of the 
       <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">
       FwpsInjectionHandleCreate0</a> function set to FWPS_INJECTION_TYPE_L2.

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



A callback driver calls the <b>FwpsInjectMacReceiveAsync0</b>  function to reinject a previously absorbed MAC frame (or a clone of the frame) back to the layer 2 inbound data path from which it was intercepted, or to inject an invented MAC frame.

The <i>netBufferLists</i> parameter can be a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> chain. However the completion function could be invoked multiple times each, completing a segment (or single NET_BUFFER_LIST) of the chain.



Injected frames could get classified again if the packets match the same filter as originally classified. Therefore, as with callouts at IP layers, layer 2 callouts must also protect against infinite packet inspection by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocateclonenetbufferlist0">
     FwpsAllocateCloneNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsallocatenetbufferandnetbufferlist0">
     FwpsAllocateNetBufferAndNetBufferList0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsinjectionhandlecreate0">
       FwpsInjectionHandleCreate0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nf-fwpsk-fwpsquerypacketinjectionstate0">FwpsQueryPacketInjectionState0</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">classifyFn</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fwpsk/nc-fwpsk-fwps_inject_complete0">completionFn</a>
 

 

