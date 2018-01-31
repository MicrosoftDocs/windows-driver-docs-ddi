---
UID: NF:ndischimney.NdisOffloadTcpSend
title: NdisOffloadTcpSend function
author: windows-driver-content
description: A protocol driver or intermediate driver calls the NdisOffloadTcpSend function to transmit data on an offloaded TCP connection.
old-location: netvista\ndisoffloadtcpsend.htm
old-project: netvista
ms.assetid: a2743bbb-a6fa-4b7e-8087-132e221a5624
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisoffloadtcpsend, NdisOffloadTcpSend function [Network Drivers Starting with Windows Vista], tcp_chim_ndis_func_51f71d27-0877-4046-b80d-8c05765d8e69.xml, NdisOffloadTcpSend, ndischimney/NdisOffloadTcpSend
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisOffloadTcpSend
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisOffloadTcpSend function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or intermediate driver calls the 
  <b>NdisOffloadTcpSend</b> function to transmit data on an offloaded TCP connection.


## -syntax


````
NDIS_STATUS NdisOffloadTcpSend(
  _In_ PNDIS_OFFLOAD_HANDLE NdisOffloadHandle,
  _In_ PNET_BUFFER_LIST     NetBufferList
);
````


## -parameters




#### - NdisOffloadHandle [in]

A handle to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <mshelp:link keywords="netvista.referencing_offloaded_state_through_an_intermediate_driver" tabindex="0">
     Referencing Offloaded State Through an Intermediate Driver</mshelp:link>.


#### - NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes a list of 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures. Each NET_BUFFER structure
     in the list points to a chain of memory descriptor lists (MDLs). The MDLs contain the data to be
     transmitted. The NET_BUFFER_LIST and associated structures are locked so that they remain resident in
     physical memory. However, they are not mapped into system memory.


## -returns


The 
     <b>NdisOffloadTcpSend</b> function always returns NDIS_STATUS_PENDING. The send operation is always
     completed asynchronously.



## -remarks


In response to a call to its 
    <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a> function,
    an intermediate driver calls the 
    <b>NdisOffloadTcpSend</b> function to propagate the send operation to the underlying intermediate driver
    or offload target. For more information, see 
    <a href="https://msdn.microsoft.com/009159ad-81c0-4555-8e6b-a4fec2c7f1d5">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpSend</b> function, the intermediate driver passes the following:
<ul>
<li>
An 
      <i>NdisOffloadHandle</i> that references the NDIS_OFFLOAD_HANDLE structure stored in the intermediate
      driver's context for the offloaded TCP connection. For more information, see 
      <mshelp:link keywords="netvista.referencing_offloaded_state_through_an_intermediate_driver" tabindex="0">
      Referencing Offloaded State Through an Intermediate Driver</mshelp:link>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadSend</i> function.

</li>
</ul>When the underlying driver or offload target subsequently completes the send operation by calling the 
    <b>NdisTcpOffloadSendComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadSendComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadSendComplete</b> function to propagate the completion of the send operation.



## -see-also

<mshelp:link keywords="netvista.protocoltcpoffloadsendcomplete" tabindex="0"><i>
   ProtocolTcpOffloadSendComplete</i></mshelp:link>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a>

<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">NdisTcpOffloadSendComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOffloadTcpSend function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

