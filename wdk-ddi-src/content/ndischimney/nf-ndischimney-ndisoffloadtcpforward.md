---
UID: NF:ndischimney.NdisOffloadTcpForward
title: NdisOffloadTcpForward function
author: windows-driver-content
description: A protocol driver or an intermediate driver calls the NdisOffloadTcpForward function to forward unacknowledged received TCP segments to an underlying driver or offload target.
old-location: netvista\ndisoffloadtcpforward.htm
old-project: netvista
ms.assetid: ca4e26c5-5fea-42ab-aee6-3ecf4cce3798
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisOffloadTcpForward function [Network Drivers Starting with Windows Vista], netvista.ndisoffloadtcpforward, ndischimney/NdisOffloadTcpForward, tcp_chim_ndis_func_9def62ce-e860-4f98-a609-8e96e6381c66.xml, NdisOffloadTcpForward
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
-	NdisOffloadTcpForward
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisOffloadTcpForward function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or an intermediate driver calls the 
  <b>NdisOffloadTcpForward</b> function to forward unacknowledged received TCP segments to an underlying
  driver or offload target.


## -syntax


````
NDIS_STATUS NdisOffloadTcpForward(
  _In_ PNDIS_OFFLOAD_HANDLE NdisOffloadHandle,
  _In_ PNET_BUFFER_LIST     NetBufferList
);
````


## -parameters




### -param NdisOffloadHandle [in]

A handle to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.


### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure. Each NET_BUFFER structure
     points to a chain of memory descriptor lists (MDLs). The MDLs associated with a NET_BUFFER structure
     contain one and only one TCP segment that is being forwarded to the offload target. The first byte of
     the first MDL is the first byte of the TCP header. The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.


## -returns



The 
     <b>NdisOffloadTcpForward</b> function always returns NDIS_STATUS_PENDING. The forward operation is always
     completed asynchronously.




## -remarks



In response to a call to its 
    <i>MiniportTcpOffloadForward</i> function, an intermediate driver calls the 
    <b>NdisOffloadTcpForward</b> function to propagate the forward operation to the underlying driver or
    offload target. For more information, see 
    <a href="https://msdn.microsoft.com/009159ad-81c0-4555-8e6b-a4fec2c7f1d5">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpForward</b> function, the intermediate driver passes the following:

<ul>
<li>
An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">
      MiniportTcpOffloadForward</a> function.

</li>
</ul>
When the underlying driver or offload target subsequently completes the forward operation by calling
    the 
    <b>NdisTcpOffloadForwardComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadForwardComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadForwardComplete</b> function to propagate the completion of the forward operation.




## -see-also

<a href="..\ndischimney\nc-ndischimney-tcp_offload_forward_complete_handler.md">
   ProtocolTcpOffloadForwardComplete</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_forward_complete.md">
   NdisTcpOffloadForwardComplete</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>



<a href="..\ndischimney\nc-ndischimney-tcp_offload_forward_complete_handler.md">
   ProtocolTcpOffloadForwardComplete</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_offload_handle.md">NDIS_OFFLOAD_HANDLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOffloadTcpForward function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

