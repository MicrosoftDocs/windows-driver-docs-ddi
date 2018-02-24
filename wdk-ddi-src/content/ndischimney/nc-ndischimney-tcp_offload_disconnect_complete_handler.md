---
UID: NC:ndischimney.TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER
title: TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol driver's or intermediate driver's ProtocolTcpOffloadDisconnectComplete function to complete a disconnect operation that the driver previously initiated by calling the NdisOffloadTcpDisconnect function.
old-location: netvista\protocoltcpoffloaddisconnectcomplete.htm
old-project: netvista
ms.assetid: 56244148-638f-4d93-82a6-2cced9744046
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.protocoltcpoffloaddisconnectcomplete, ProtocolTcpOffloadDisconnectComplete callback function [Network Drivers Starting with Windows Vista], ProtocolTcpOffloadDisconnectComplete, TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER, TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER, ndischimney/ProtocolTcpOffloadDisconnectComplete, tcp_chim_protocol_func_fadc0ea9-acd8-489d-886c-213b909d93b3.xml
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
-	ProtocolTcpOffloadDisconnectComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolTcpOffloadDisconnectComplete</i> function to complete a disconnect operation that the driver
  previously initiated by calling the 
  <a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpdisconnect.md">
  NdisOffloadTcpDisconnect</a> function.


## -prototype


````
TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER ProtocolTcpOffloadDisconnectComplete;

VOID ProtocolTcpOffloadDisconnectComplete(
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

When non-NULL, a pointer to a single 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpdisconnect.md">
     NdisOffloadTcpDisconnect</a> function.


## -returns



None




## -remarks



In response to an underlying driver's or offload target's call to the 
    <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_disconnect_complete.md">
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
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff568388">
    NET_BUFFER_LIST_CONTEXT</a> structure, which is associated with the NET_BUFFER_LIST structure.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpdisconnect.md">NdisOffloadTcpDisconnect</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_disconnect_complete.md">
   NdisTcpOffloadDisconnectComplete</a>



<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
   MiniportTcpOffloadDisconnect</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

