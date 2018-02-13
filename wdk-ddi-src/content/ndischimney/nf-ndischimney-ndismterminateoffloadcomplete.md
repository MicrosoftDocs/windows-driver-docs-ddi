---
UID: NF:ndischimney.NdisMTerminateOffloadComplete
title: NdisMTerminateOffloadComplete function
author: windows-driver-content
description: An offload target calls the NdisMTerminateOffloadComplete function to complete a terminate offload operation that was initiated by a previous call to the MiniportTerminateOffload function of the offload target.
old-location: netvista\ndismterminateoffloadcomplete.htm
old-project: netvista
ms.assetid: d444eae5-2e7c-41f2-9fb2-55e172505cf6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMTerminateOffloadComplete, NdisMTerminateOffloadComplete function [Network Drivers Starting with Windows Vista], tcp_chim_ndis_func_3e692d5c-5cad-4567-8639-76f97bf2e39c.xml, ndischimney/NdisMTerminateOffloadComplete, netvista.ndismterminateoffloadcomplete
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndischimney.h
apiname:
-	NdisMTerminateOffloadComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisMTerminateOffloadComplete function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMTerminateOffloadComplete</b> function to complete a terminate offload operation that was initiated
  by a previous call to the 
  <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
  MiniportTerminateOffload</a> function of the offload target.


## -syntax


````
VOID NdisMTerminateOffloadComplete(
  _In_ NDIS_HANDLE                       NdisMiniportHandle,
  _In_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a>.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The offload target obtained this pointer as an input
     parameter to its 
     <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
     MiniportTerminateOffload</a> function.


## -returns



None




## -remarks



Before calling the 
    <b>NdisMTerminateOffloadComplete</b> function, the offload target must write either of the following
    NDIS_STATUS values to the 
    <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree:

<ul>
<li>
NDIS_STATUS_SUCCESS

The offload target successfully terminated the offload of the state object referenced by the
      NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure. If the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure is
      followed by a delegated state structure (<i>XXX</i>_OFFLOAD_STATE_DELEGATED), the offload target successfully wrote the delegated variable
      values for that state object to the delegated state structure.

</li>
<li>
NDIS_STATUS_FAILURE

The terminate operation did not succeed. Such a failure is caused by a catastrophic failure that
      resulted in the loss of the state object that was to be terminated. In this case, the offload target
      hardware might not be responding. The host stack might have to abort the connection.

</li>
</ul>
Before calling the 
    <b>NdisMTerminateOffloadComplete</b> function, the offload target must also:

<ul>
<li>
Complete any oustanding calls to the 
      <a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">MiniportInvalidateOffload</a>,
      
      <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>, 
      <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">MiniportTcpOffloadReceive</a>,
      
      <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
      MiniportTcpOffloadDisconnect</a>, 
      <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>,
      
      <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a>, and 
      <a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">
      MiniportUpdateOffload</a> functions.

</li>
<li>
Ensure that any outstanding calls to the 
      <a href="..\ndis\nf-ndis-ndismindicatestatusex.md">NdisMIndicateStatusEx</a>, 
      <a href="..\ndischimney\nf-ndischimney-ndismoffloadeventindicate.md">NdisMOffloadEventIndicate</a>, 
      <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">NdisTcpOffloadEventHandler</a>,
      and 
      <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">
      NdisTcpOffloadReceiveHandler</a> functions have returned.

</li>
</ul>
If there is outstanding send data on a TCP connection that is being terminated, the offload target
    packages such data in net buffers and passes the packaged data to the host stack in a linked list of 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures. In this case,
    the offload target specifies a non-<b>NULL</b> value for the 
    <b>NetBufferListChain</b> member of the NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure for that connection.
    (The NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure is in the linked list pointed to by the 
    <i>OffloadBlockList</i> pointer.) The 
    <b>NetBufferListChain</b> member points to the linked list of 
    <b>NET_BUFFER_LIST</b> structures with which the
    send data is associated.

When passing outstanding send data to the host stack, the offload target must also specify non-<b>NULL</b>
    values for the following delegated TCP variables for the connection that is being terminated:

<ul>
<li>
SndUna

</li>
<li>
SndNxt

</li>
<li>
SndMax

</li>
</ul>
For more information about passing outstanding send data, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/handling-outstanding-send-data-during-and-after-an-offload-operation">
    Handling Outstanding Send Data During and After an Offload Operation</a>.

If there is no outstanding send data on a TCP connection that is being terminated, the offload target
    must specify a <b>NULL</b> value for the 
    <b>NetBufferListChain</b> member.

There might be outstanding receive data on a TCP connection that is being uploaded. This is data that
    the offload target has received off the wire, processed, and acknowledged. For more information about
    processing such data, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/push-timer">
    Handling Buffered Receive Data During a Terminate Offload Operation</a>.

The offload target frees all resources, such as memory, that are associated with the terminated state
    objects.




## -see-also

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndischimney\ns-ndischimney-_tcp_offload_state_delegated.md">TCP_OFFLOAD_STATE_DELEGATED</a>



<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMTerminateOffloadComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

