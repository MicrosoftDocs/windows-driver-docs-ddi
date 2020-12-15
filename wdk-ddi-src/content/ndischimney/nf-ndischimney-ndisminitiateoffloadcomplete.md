---
UID: NF:ndischimney.NdisMInitiateOffloadComplete
title: NdisMInitiateOffloadComplete function (ndischimney.h)
description: An offload target calls the NdisMInitiateOffloadComplete function to complete an offload operation that was initiated by a previous call to the MiniportInitiateOffload function.
old-location: netvista\ndisminitiateoffloadcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMInitiateOffloadComplete function"]
ms.keywords: NdisMInitiateOffloadComplete, NdisMInitiateOffloadComplete function [Network Drivers Starting with Windows Vista], ndischimney/NdisMInitiateOffloadComplete, netvista.ndisminitiateoffloadcomplete, tcp_chim_ndis_func_e5917638-7b7e-49e6-afad-63bbb3490cd9.xml
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
req.lib: 
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMInitiateOffloadComplete
 - ndischimney/NdisMInitiateOffloadComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndischimney.h
api_name:
 - NdisMInitiateOffloadComplete
---

# NdisMInitiateOffloadComplete function


## -description

<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMInitiateOffloadComplete</b> function to complete an offload operation that was initiated by a
  previous call to the 
  <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_initiate_offload_handler">
  MiniportInitiateOffload</a> function.

## -parameters

### -param NdisMiniportHandle 

[in]
The handle that the offload target obtained in a previous call to 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a>.

### -param OffloadBlockList 

[in]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The offload target obtained this pointer as an input
     parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_initiate_offload_handler">
     MiniportInitiateOffload</a> function.

## -remarks

Before calling 
    <b>NdisMInitiateOffloadComplete</b>, the offload target must write one of the following NDIS_STATUS
    values to the 
    <b>Status</b> member of each 
    <a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
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
    <a href="/windows-hardware/drivers/network/returning-completion-status-of-an-initiate-offload-operation">
    Returning Completion Status of an Initiate Offload Operation</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_initiate_offload_handler">MiniportInitiateOffload</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_event_indicate">NdisTcpOffloadEventHandler</a>



<a href="/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-ndis_tcp_offload_receive_indicate">NdisTcpOffloadReceiveHandler</a>



<a href="/windows-hardware/drivers/network/oid-tcp-task-offload">OID_TCP_TASK_OFFLOAD</a>
