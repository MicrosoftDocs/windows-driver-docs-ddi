---
UID: NF:ndischimney.NdisOffloadTcpDisconnect
title: NdisOffloadTcpDisconnect function
author: windows-driver-content
description: A protocol or intermediate driver calls the NdisOffloadTcpDisconnect function to close the send half of an offloaded TCP connection.
old-location: netvista\ndisoffloadtcpdisconnect.htm
old-project: netvista
ms.assetid: f8abff30-b641-4581-8532-8292993ca9f6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisOffloadTcpDisconnect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisOffloadTcpDisconnect
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: 
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisOffloadTcpDisconnect function



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisOffloadTcpDisconnect</b> function to close the send half of an offloaded TCP connection. In addition,
  if the disconnect to be performed is a graceful disconnect, the protocol or intermediate driver can supply
  application data that the underlying offload target must transmit on the offloaded TCP connection before it
  sends a FIN segment.



## -syntax

````
NDIS_STATUS NdisOffloadTcpDisconnect(
  _In_ PNDIS_OFFLOAD_HANDLE NdisOffloadHandle,
  _In_ PNET_BUFFER_LIST     NetBufferList,
  _In_ ULONG                Flags
);
````


## -parameters

### -param NdisOffloadHandle [in]

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.


### -param NetBufferList [in]

A pointer to a single 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. Only one 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure is associated with this
     NET_BUFFER_LIST structure.


### -param Flags [in]

As one of the following values, the type of disconnect to be performed:
     




### -param TCP_DISCONNECT_ABORTIVE_CLOSE

Specifies that the offload target perform an abortive disconnect by sending an RST
       segment.


### -param TCP_DISCONNECT_GRACEFUL_CLOSE

Specifies that the offload target perform a graceful disconnect by sending a FIN segment.

</dd>
</dl>

## -returns
The 
     <b>NdisOffloadTcpDisconnect</b> function always returns NDIS_STATUS_PENDING. The disconnect operation is
     always completed asynchronously.


## -remarks
In response to a call to its 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
    MiniportTcpOffloadDisconnect</a> function, an intermediate driver calls the 
    <b>NdisOffloadTcpDisconnect</b> function to propagate the disconnect operation to the underlying
    intermediate driver or offload target. For more information, see 
    <a href="https://msdn.microsoft.com/009159ad-81c0-4555-8e6b-a4fec2c7f1d5">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcp<i>Xxx</i></b>
     function, the intermediate driver passes the following:

An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadDisconnect</i> function.

The same 
      <i>Flags</i> that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadDisconnect</i> function.

When the underlying driver or offload target subsequently completes the disconnect operation by
    calling the 
    <b>NdisTcpOffloadDisconnectComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadDisconnectComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadDisconnectComplete</b> function to propagate the completion of the disconnect
    operation.


## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
   MiniportTcpOffloadDisconnect</a>
</dt>
<dt>
<a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_disconnect_complete.md">
   NdisTcpOffloadDisconnectComplete</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-tcp_offload_disconnect_complete_handler.md">
   ProtocolTcpOffloadDisconnectComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOffloadTcpDisconnect function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

