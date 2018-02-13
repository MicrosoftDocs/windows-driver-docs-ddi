---
UID: NC:ndischimney.W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER
title: W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER
author: windows-driver-content
description: NDIS calls the MiniportTcpOffloadReceiveReturn function to return ownership of NET_BUFFER_LIST and associated structures to an offload target.
old-location: netvista\miniporttcpoffloadreceivereturn.htm
old-project: netvista
ms.assetid: b746f58d-d029-4fcd-a59d-baba037fc38e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniporttcpoffloadreceivereturn, MiniportTcpOffloadReceiveReturn callback function [Network Drivers Starting with Windows Vista], MiniportTcpOffloadReceiveReturn, W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER, W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER, ndischimney/MiniportTcpOffloadReceiveReturn, tcp_chim_miniport_func_c6477511-6f31-4a37-9b28-d157e1fa09af.xml
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ndischimney.h
apiname:
-	MiniportTcpOffloadReceiveReturn
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls the 
  <i>MiniportTcpOffloadReceiveReturn</i> function to return ownership of 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> and associated structures to
  an offload target.


## -prototype


````
W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER MiniportTcpOffloadReceiveReturn;

NDIS_STATUS MiniportTcpOffloadReceiveReturn(
  _In_ NDIS_HANDLE      MiniportAdapterContext,
  _In_ PNET_BUFFER_LIST NetBufferList
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to an offload-target allocated context area in which the offload target maintains state
     information about this instance of the adapter. The miniport driver provided this handle to NDIS when it
     called 
     <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
     NdisMSetMiniportAttributes</a> from its 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">
     MiniportInitializeEx</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be a stand-alone structure or the first structure in a linked list of NET_BUFFER_LIST structures.
     The linked list can contain NET_BUFFER_LIST structures from one or more calls to the 
     <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">
     NdisTcpOffloadReceiveHandler</a> function.


## -returns



The 
     <i>MiniportTcpOffloadReceiveReturn</i> function should always succeed. Therefore, the 
     <i>MiniportTcpOffloadReceiveReturn</i> function should always return NDIS_STATUS_SUCCESS.




## -remarks



NDIS calls the 
    <i>MiniportTcpOffloadReceiveReturn</i> function to return ownership of NET_BUFFER_LIST structures and
    associated structures that the offload target passed in one or more previous calls to the 
    <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">
    NdisTcpOffloadReceiveHandler</a> function.

The 
    <i>MiniportTcpOffloadReceiveReturn</i> function can prepare a returned NET_BUFFER_LIST structure for use
    in a subsequent receive indication. Although the 
    <i>MiniportTcpOffloadReceiveReturn</i> function can return the NET_BUFFER_LIST structures to a pool (for
    example, it could call the 
    <a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a> function), it
    can be more efficient to reuse the structures without returning them to the pool.

Note that the offload target driver should not unload and the offload target adapter must not be
    closed until all indicated receive buffers have been returned.




## -see-also

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">NdisTcpOffloadReceiveHandler</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\nf-ndis-ndisfreenetbufferlist.md">NdisFreeNetBufferList</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

