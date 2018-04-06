---
UID: NC:ndischimney.TCP_OFFLOAD_SEND_COMPLETE_HANDLER
title: TCP_OFFLOAD_SEND_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadSendComplete function to complete a send operation that the driver previously initiated by calling the NdisOffloadTcpSend function.
old-location: netvista\protocoltcpoffloadsendcomplete.htm
old-project: netvista
ms.assetid: 6f9c7964-e475-421c-99d6-f4fc31a26f02
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ProtocolTcpOffloadSendComplete, ProtocolTcpOffloadSendComplete callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_SEND_COMPLETE_HANDLER, ndischimney/ProtocolTcpOffloadSendComplete, netvista.protocoltcpoffloadsendcomplete, tcp_chim_protocol_func_5d69efad-e470-44ce-850f-b7693d1a1f2e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	ProtocolTcpOffloadSendComplete
product:
- Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# TCP_OFFLOAD_SEND_COMPLETE_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadSendComplete</i> function to complete a send operation that the driver previously
  initiated by calling the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff563708">NdisOffloadTcpSend</a> function.


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     might be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <b>NdisOffloadTcpSend</b> function.


## -returns



None




## -remarks



In response to an underlying driver's or offload target's call to the 
    <a href="https://msdn.microsoft.com/1689b6f9-88f3-456f-9a7c-c6b4e76cb336">
    NdisOffloadTcpSendComplete</a> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadSendComplete</i> function.

To propagate the completion of the I/O operation to the overlying driver or host stack, the
    intermediate driver itself calls the 
    <b>NdisOffloadTcpSendComplete</b> function, passing in the following:

<ul>
<li>
A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

</li>
<li>
The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadSendComplete</i> function.

</li>
</ul>
In response, NDIS calls the overyling driver's 
    <i>ProtocolTcpOffloadSendComplete</i> function, passing a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpSendComplete</b> function.




## -see-also




<a href="https://msdn.microsoft.com/7c96412f-a866-4863-a06a-9eb6adb2a33b">MiniportTcpSendOffload</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563708">NdisOffloadTcpSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564609">NdisTcpOffloadSendComplete</a>
 

 

