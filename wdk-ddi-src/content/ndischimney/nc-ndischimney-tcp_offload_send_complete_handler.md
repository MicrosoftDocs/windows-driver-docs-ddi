---
UID: NC:ndischimney.TCP_OFFLOAD_SEND_COMPLETE_HANDLER
title: TCP_OFFLOAD_SEND_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadSendComplete function to complete a send operation that the driver previously initiated by calling the NdisOffloadTcpSend function.
old-location: netvista\protocoltcpoffloadsendcomplete.htm
old-project: netvista
ms.assetid: 6f9c7964-e475-421c-99d6-f4fc31a26f02
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.protocoltcpoffloadsendcomplete, ProtocolTcpOffloadSendComplete callback function [Network Drivers Starting with Windows Vista], ProtocolTcpOffloadSendComplete, TCP_OFFLOAD_SEND_COMPLETE_HANDLER, TCP_OFFLOAD_SEND_COMPLETE_HANDLER, ndischimney/ProtocolTcpOffloadSendComplete, tcp_chim_protocol_func_5d69efad-e470-44ce-850f-b7693d1a1f2e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndischimney.h
apiname:
-	ProtocolTcpOffloadSendComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# TCP_OFFLOAD_SEND_COMPLETE_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadSendComplete</i> function to complete a send operation that the driver previously
  initiated by calling the 
  <a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpsend.md">NdisOffloadTcpSend</a> function.


## -prototype


````
TCP_OFFLOAD_SEND_COMPLETE_HANDLER ProtocolTcpOffloadSendComplete;

VOID ProtocolTcpOffloadSendComplete(
  _In_ NDIS_HANDLE                       ProtocolBindingContext,
  _In_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST NetBufferList
)
{ ... }
````


## -parameters




### -param ProtocolBindingContext [in]

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     might be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <b>NdisOffloadTcpSend</b> function.


## -returns


None



## -remarks


In response to an underlying driver's or offload target's call to the 
    <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">
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
</ul>In response, NDIS calls the overyling driver's 
    <i>ProtocolTcpOffloadSendComplete</i> function, passing a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpSendComplete</b> function.



## -see-also

<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpSendOffload</a>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NET_BUFFER_LIST</a>

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_send_complete.md">NdisTcpOffloadSendComplete</a>

<a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpsend.md">NdisOffloadTcpSend</a>

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_SEND_COMPLETE_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

