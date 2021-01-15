---
UID: NC:ndischimney.TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER
title: TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol driver's or intermediate driver's ProtocolTcpOffloadDisconnectComplete function to complete a disconnect operation that the driver previously initiated by calling the NdisOffloadTcpDisconnect function.
old-location: netvista\protocoltcpoffloaddisconnectcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER callback function"]
ms.keywords: ProtocolTcpOffloadDisconnectComplete, ProtocolTcpOffloadDisconnectComplete callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER, TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER callback, ndischimney/ProtocolTcpOffloadDisconnectComplete, netvista.protocoltcpoffloaddisconnectcomplete, tcp_chim_protocol_func_fadc0ea9-acd8-489d-886c-213b909d93b3.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER
 - ndischimney/TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndischimney.h
api_name:
 - TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER
---

# TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER callback function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolTcpOffloadDisconnectComplete</i> function to complete a disconnect operation that the driver
  previously initiated by calling the 
  <a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisoffloadtcpdisconnect">
  NdisOffloadTcpDisconnect</a> function.

## -parameters

### -param ProtocolBindingContext 

[in]
A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function.

### -param NetBufferList 

[in]
When non-NULL, a pointer to a single 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a> structure. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisoffloadtcpdisconnect">
     NdisOffloadTcpDisconnect</a> function.

## -remarks

In response to an underlying driver's or offload target's call to the 
    <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
    NdisTcpOffloadDisconnectComplete</a> function, NDIS calls the overlying protocol driver's or
    intermediate driver's 
    <i>ProtocolTcpOffloadDisconnectComplete</i> function.

To propagate the completion of the disconnect operation to the overlying driver, the intermediate
    driver calls the 
    <b>NdisOffloadTcpDisconnectComplete</b> function, passing in the following:

<ul>
<li>
A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadDisconnectComplete</i> function.

</li>
</ul>
In response, NDIS calls the overlying driver's 
    <i>ProtocolTcpOffloadDisconnectComplete</i> function, passing a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer passed by the intermediate driver to
    the 
    <b>NdisOffloadTcpDisconnectComplete</b> function.

Before returning, the 
    <i>ProtocolTcpOffloadDisconnectComplete</i> function should deallocate the memory for any context that it
    created for the NET_BUFFER_LIST structure that was passed to the function.

Note that, if an intermediate driver exports more than one interface to overlying protocols, it must
    determine which protocol should receive the completion of the disconnect. To make this determination, the
    intermediate driver uses information that it stored in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">
    NET_BUFFER_LIST_CONTEXT</a> structure, which is associated with the NET_BUFFER_LIST structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_tcp_offload_disconnect_handler">
   MiniportTcpOffloadDisconnect</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_net_buffer_list">NET_BUFFER_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nf-ndischimney-ndisoffloadtcpdisconnect">NdisOffloadTcpDisconnect</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_disconnect_complete">
   NdisTcpOffloadDisconnectComplete</a>

