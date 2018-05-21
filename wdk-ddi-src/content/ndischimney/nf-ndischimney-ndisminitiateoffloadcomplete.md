---
UID: NF:ndischimney.NdisMInitiateOffloadComplete
title: NdisMInitiateOffloadComplete function
author: windows-driver-content
description: An offload target calls the NdisMInitiateOffloadComplete function to complete an offload operation that was initiated by a previous call to the MiniportInitiateOffload function.
old-location: netvista\ndisminitiateoffloadcomplete.htm
old-project: netvista
ms.assetid: 983b2e04-1563-4f2e-85a7-8fd93ec1cd8c
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: NdisMInitiateOffloadComplete, NdisMInitiateOffloadComplete function [Network Drivers Starting with Windows Vista], ndischimney/NdisMInitiateOffloadComplete, netvista.ndisminitiateoffloadcomplete, tcp_chim_ndis_func_e5917638-7b7e-49e6-afad-63bbb3490cd9.xml
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	NdisMInitiateOffloadComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMInitiateOffloadComplete function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMInitiateOffloadComplete</b> function to complete an offload operation that was initiated by a
  previous call to the 
  <a href="https://msdn.microsoft.com/f430642b-01bf-4ed7-bfea-e8dd8d5a8208">
  MiniportInitiateOffload</a> function.


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a>.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The offload target obtained this pointer as an input
     parameter to its 
     <a href="https://msdn.microsoft.com/f430642b-01bf-4ed7-bfea-e8dd8d5a8208">
     MiniportInitiateOffload</a> function.


## -returns



None




## -remarks



Before calling 
    <b>NdisMInitiateOffloadComplete</b>, the offload target must write one of the following NDIS_STATUS
    values to the 
    <b>Status</b> member of each 
    <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
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




<a href="https://msdn.microsoft.com/f430642b-01bf-4ed7-bfea-e8dd8d5a8208">MiniportInitiateOffload</a>



<a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564595">NdisTcpOffloadEventHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564606">NdisTcpOffloadReceiveHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569816">OID_TCP_TASK_OFFLOAD</a>
 

 

