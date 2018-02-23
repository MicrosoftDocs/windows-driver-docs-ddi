---
UID: NF:ndischimney.NdisMInitiateOffloadComplete
title: NdisMInitiateOffloadComplete function
author: windows-driver-content
description: An offload target calls the NdisMInitiateOffloadComplete function to complete an offload operation that was initiated by a previous call to the MiniportInitiateOffload function.
old-location: netvista\ndisminitiateoffloadcomplete.htm
old-project: netvista
ms.assetid: 983b2e04-1563-4f2e-85a7-8fd93ec1cd8c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: tcp_chim_ndis_func_e5917638-7b7e-49e6-afad-63bbb3490cd9.xml, netvista.ndisminitiateoffloadcomplete, NdisMInitiateOffloadComplete function [Network Drivers Starting with Windows Vista], NdisMInitiateOffloadComplete, ndischimney/NdisMInitiateOffloadComplete
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
-	NdisMInitiateOffloadComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisMInitiateOffloadComplete function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMInitiateOffloadComplete</b> function to complete an offload operation that was initiated by a
  previous call to the 
  <a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">
  MiniportInitiateOffload</a> function.


## -syntax


````
VOID NdisMInitiateOffloadComplete(
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
     <a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">
     MiniportInitiateOffload</a> function.


## -returns



None




## -remarks



Before calling 
    <b>NdisMInitiateOffloadComplete</b>, the offload target must write one of the following NDIS_STATUS
    values to the 
    <b>Status</b> member of each 
    <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure in the state tree passed to the offload target's 
    <i>MiniportInitiateOffload</i> function:

<ul>
<li>
NDIS_STATUS_SUCCESS

</li>
<li>
NDIS_STATUS_PARTIAL_SUCCESS

</li>
<li>
NDIS_STATUS_RESOURCES

</li>
<li>
NDIS_STATUS_OFFLOAD_TCP_ENTRIES

</li>
<li>
NDIS_STATUS_OFFLOAD_PATH_ENTRIES

</li>
<li>
NDIS_STATUS_OFFLOAD_NEIGHBOR_ENTRIES

</li>
<li>
NDIS_STATUS_OFFLOAD_HW_ADDRESS_ENTRIES

</li>
<li>
NDIS_STATUS_OFFLOAD_IP_ADDRESS_ENTRIES

</li>
<li>
NDIS_STATUS_OFFLOAD_TCP_XMIT_BUFFER

</li>
<li>
NDIS_STATUS_OFFLOAD_TCP_RCV_BUFFER

</li>
<li>
NDIS_STATUS_OFFLOAD_TCP_RCV_WINDOW

</li>
<li>
NDIS_STATUS_OFFLOAD_VLAN_ENTRIES

</li>
<li>
NDIS_STATUS_OFFLOAD_PATH_MTU

</li>
<li>
NDIS_STATUS_FAILURE

</li>
</ul>
For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/returning-completion-status-of-an-initiate-offload-operation">
    Returning Completion Status of an Initiate Offload Operation</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569816">OID_TCP_TASK_OFFLOAD</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_indicate.md">NdisTcpOffloadReceiveHandler</a>



<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_event_indicate.md">NdisTcpOffloadEventHandler</a>



<a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">MiniportInitiateOffload</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMInitiateOffloadComplete function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

