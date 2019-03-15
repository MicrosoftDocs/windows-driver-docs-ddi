---
UID: NC:ndischimney.TCP_OFFLOAD_RECV_COMPLETE_HANDLER
title: TCP_OFFLOAD_RECV_COMPLETE_HANDLER (ndischimney.h)
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadReceiveComplete function to complete a receive operation that the driver previously initiated by calling the NdisOffloadTcpReceive function.
old-location: netvista\protocoltcpoffloadreceivecomplete.htm
tech.root: netvista
ms.assetid: 78201512-6b70-4b4b-9016-0f42fed41ac6
ms.date: 05/02/2018
ms.keywords: ProtocolTcpOffloadReceiveComplete, ProtocolTcpOffloadReceiveComplete callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_RECV_COMPLETE_HANDLER, TCP_OFFLOAD_RECV_COMPLETE_HANDLER callback, ndischimney/ProtocolTcpOffloadReceiveComplete, netvista.protocoltcpoffloadreceivecomplete, tcp_chim_protocol_func_3f02ff3b-3b86-4a30-8022-2c540b5e9484.xml
ms.topic: callback
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ndischimney.h
api_name:
- ProtocolTcpOffloadReceiveComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# TCP_OFFLOAD_RECV_COMPLETE_HANDLER callback function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadReceiveComplete</i> function to complete a receive operation that the driver previously
  initiated by calling the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff563703">NdisOffloadTcpReceive</a> function.


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <a href="https://msdn.microsoft.com/021f41c4-6ba9-418e-bc18-131ce6d90877">
     NdisOffloadTcpReceive</a> function.


## -returns



None




## -remarks



In response to an underlying driver's or offload target's call to the 
    <a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
    NdisOffloadTcpReceiveComplete</a> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function.

To propagate the completion of the I/O operation to the overlying driver, the intermediate driver
    itself calls the 
    <b>NdisOffloadTcpReceiveComplete</b> function, passing in the following:

<ul>
<li>
A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

</li>
<li>
The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadReceiveComplete</i> function.

</li>
</ul>
In response, NDIS calls the overlying driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function, passing a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpReceiveComplete</b> function.




## -see-also




<a href="https://msdn.microsoft.com/9c9c033d-e892-4d8a-8f12-4ca34cdc9ea1">MiniportTcpOffloadReceive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563703">NdisOffloadTcpReceive</a>



<a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
   NdisOffloadTcpReceiveComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>
 

 

