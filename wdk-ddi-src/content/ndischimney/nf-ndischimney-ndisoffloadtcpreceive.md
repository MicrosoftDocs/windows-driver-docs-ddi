---
UID: NF:ndischimney.NdisOffloadTcpReceive
title: NdisOffloadTcpReceive function
author: windows-driver-content
description: A protocol driver or an intermediate driver calls the NdisOffloadTcpReceive function to post receive requests (receive buffers) on an offloaded TCP connection.
old-location: netvista\ndisoffloadtcpreceive.htm
tech.root: netvista
ms.assetid: 021f41c4-6ba9-418e-bc18-131ce6d90877
ms.date: 05/02/2018
ms.keywords: NdisOffloadTcpReceive, NdisOffloadTcpReceive function [Network Drivers Starting with Windows Vista], ndischimney/NdisOffloadTcpReceive, netvista.ndisoffloadtcpreceive, tcp_chim_ndis_func_601c3cd9-00c3-425b-a42e-c8ea8563bde3.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisOffloadTcpReceive
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisOffloadTcpReceive function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol driver or an intermediate driver calls the 
  <b>NdisOffloadTcpReceive</b> function to post receive requests (receive buffers) on an offloaded TCP
  connection.


## -parameters




### -param NdisOffloadHandle [in]

A handle to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a> structure in the
     caller's context for the offloaded TCP connection. For more information, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
     Referencing Offloaded State Through an Intermediate Driver</a>.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     Each NET_BUFFER_LIST structure in the list describes one 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure. The NET_BUFFER structure
     points to a chain of memory descriptor lists (MDLs). The NET_BUFFER_LIST and associated structures are
     locked so that they remain resident in physical memory. However, they are not mapped into system
     memory.


## -returns



The 
     <b>NdisOffloadTcpReceive</b> function always returns NDIS_STATUS_PENDING. The receive operation is always
     completed asynchronously.




## -remarks



In response to a call to its 
    <a href="https://msdn.microsoft.com/9c9c033d-e892-4d8a-8f12-4ca34cdc9ea1">
    MiniportTcpOffloadReceive</a> function, an intermediate driver calls the 
    <b>NdisOffloadTcpReceive</b> function to propagate the receive operation to the underlying intermediate
    driver or offload target. For more information, see 
    <a href="https://msdn.microsoft.com/009159ad-81c0-4555-8e6b-a4fec2c7f1d5">Propagating I/O Operations</a>.

To the 
    <b>NdisOffloadTcpReceive</b> function, the intermediate driver passes the following:

<ul>
<li>
An 
      <i>NdisOffloadHandle</i> function that references the NDIS_OFFLOAD_HANDLE structure stored in the
      intermediate driver's context for the offloaded TCP connection. For more information, see 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/network/referencing-offloaded-state-through-an-intermediate-driver">
      Referencing Offloaded State Through an Intermediate Driver</a>.

</li>
<li>
The same PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>MiniportTcpOffloadReceive</i> function.

</li>
</ul>
When the underlying driver or offload target subsequently completes the receive operation by calling
    the 
    <b>NdisTcpOffloadReceiveComplete</b> function, NDIS calls the intermediate driver's 
    <i>ProtocolOffloadReceiveComplete</i> function. The intermediate driver then calls the 
    <b>NdisTcpOffloadReceiveComplete</b> function to propagate the completion of the forward operation.




## -see-also




<a href="https://msdn.microsoft.com/9c9c033d-e892-4d8a-8f12-4ca34cdc9ea1">MiniportTcpOffloadReceive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566705">NDIS_OFFLOAD_HANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
   NdisTcpOffloadReceiveComplete</a>



<a href="https://msdn.microsoft.com/78201512-6b70-4b4b-9016-0f42fed41ac6">
   ProtocolTcpOffloadReceiveComplete</a>
 

 

