---
UID: NF:ndischimney.NdisMQueryOffloadStateComplete
title: NdisMQueryOffloadStateComplete function (ndischimney.h)
description: An offload target calls the NdisMQueryOffloadStateComplete function to complete a query offload operation that was initiated by a previous call to the offload target's MiniportQueryOffload function.
old-location: netvista\ndismqueryoffloadstatecomplete.htm
tech.root: netvista
ms.assetid: 7bcc6610-0c48-4a7f-b8fa-be372af201ba
ms.date: 05/02/2018
keywords: ["NdisMQueryOffloadStateComplete function"]
ms.keywords: NdisMQueryOffloadStateComplete, NdisMQueryOffloadStateComplete function [Network Drivers Starting with Windows Vista], ndischimney/NdisMQueryOffloadStateComplete, netvista.ndismqueryoffloadstatecomplete, tcp_chim_ndis_func_505090bf-b327-439e-886e-784bb5f44b00.xml
f1_keywords:
 - "ndischimney/NdisMQueryOffloadStateComplete"
 - "NdisMQueryOffloadStateComplete"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndischimney.h
api_name:
- NdisMQueryOffloadStateComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMQueryOffloadStateComplete function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMQueryOffloadStateComplete</b> function to complete a query offload operation that was initiated by a
  previous call to the offload target's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_query_offload_handler">
  MiniportQueryOffload</a> function.


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload driver obtained in a previous call to 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a>.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The offload target obtained this pointer as an input
     parameter to its 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_query_offload_handler">
     MiniportQueryOffload</a> function.


## -remarks



An offload target calls 
    <b>NdisMQueryOffloadStateComplete</b> to complete a query operation that was initiated when NDIS called
    the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_query_offload_handler">MiniportQueryOffload</a> function of
    the offload target.

Before calling 
    <b>NdisMQueryOffloadStateComplete</b>, the offload target must:

<ul>
<li>
Fill in each 
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_tcp_offload_state_delegated">offload state structure</a> in the state
      tree with the current values of that structure's variables.

</li>
<li>
Write a status value of NDIS_STATUS_SUCCESS or NDIS_STATUS_FAILURE to the 
      <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree.

</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/nc-ndischimney-w_query_offload_handler">MiniportQueryOffload</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndischimney/ns-ndischimney-_ndis_miniport_offload_block_list">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>
 

 

