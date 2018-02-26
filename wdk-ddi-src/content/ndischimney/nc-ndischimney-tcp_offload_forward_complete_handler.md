---
UID: NC:ndischimney.TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
title: TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadForwardComplete function to complete a forward operation that the driver previously initiated by calling the NdisOffloadTcpForward function.
old-location: netvista\protocoltcpoffloadforwardcomplete.htm
old-project: netvista
ms.assetid: 02a11841-d98a-4c74-8922-458826e2911e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ProtocolTcpOffloadForwardComplete, ProtocolTcpOffloadForwardComplete callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER, ndischimney/ProtocolTcpOffloadForwardComplete, netvista.protocoltcpoffloadforwardcomplete, tcp_chim_protocol_func_18981e3f-fec9-483d-b60e-54017ebd57d1.xml
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
-	ProtocolTcpOffloadForwardComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadForwardComplete</i> function to complete a forward operation that the driver previously
  initiated by calling the 
  <a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpdisconnect.md">
  NdisOffloadTcpForward</a> function.


## -prototype


````
TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER ProtocolTcpOffloadForwardComplete;

VOID ProtocolTcpOffloadForwardComplete(
  _In_ NDIS_HANDLE      ProtocolBindingContext,
  _In_ PNET_BUFFER_LIST NetBufferList
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
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <b>NdisOffloadTcpForward</b> function.


## -returns



None




## -remarks



In response to an underlying driver's or offload target's call to the 
    <b>NdisOffloadTcpForwardComplete</b> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadForwardComplete</i> function.

To propagate the completion of the forward operation to the overlying driver or host stack, the
    intermediate driver calls the 
    <b>NdisOffloadTcpForwardComplete</b> function, passing in the following:

<ul>
<li>
A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

</li>
<li>
The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadForwardComplete</i> function.

</li>
</ul>
In response, NDIS calls the overlying driver's or host stack's 
    <i>ProtocolTcpOffloadForwardComplete</i> function, passing in a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpForwardComplete</b> function.




## -see-also

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_forward_complete.md">
   NdisTcpOffloadForwardComplete</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpdisconnect.md">NdisOffloadTcpForward</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

