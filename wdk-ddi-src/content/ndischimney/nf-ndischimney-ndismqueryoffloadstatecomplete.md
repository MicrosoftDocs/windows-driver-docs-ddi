---
UID: NF:ndischimney.NdisMQueryOffloadStateComplete
title: NdisMQueryOffloadStateComplete function
author: windows-driver-content
description: An offload target calls the NdisMQueryOffloadStateComplete function to complete a query offload operation that was initiated by a previous call to the offload target's MiniportQueryOffload function.
old-location: netvista\ndismqueryoffloadstatecomplete.htm
old-project: netvista
ms.assetid: 7bcc6610-0c48-4a7f-b8fa-be372af201ba
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMQueryOffloadStateComplete
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
req.alt-api: NdisMQueryOffloadStateComplete
req.alt-loc: ndischimney.h
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
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisMQueryOffloadStateComplete function



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisMQueryOffloadStateComplete</b> function to complete a query offload operation that was initiated by a
  previous call to the offload target's 
  <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">
  MiniportQueryOffload</a> function.



## -syntax

````
VOID NdisMQueryOffloadStateComplete(
  _In_ NDIS_HANDLE                       NdisMiniportHandle,
  _In_ PNDIS_MINIPORT_OFFLOAD_BLOCK_LIST OffloadBlockList
);
````


## -parameters

### -param NdisMiniportHandle [in]

The handle that the offload driver obtained in a previous call to 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a>.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
     NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. The offload target obtained this pointer as an input
     parameter to its 
     <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">
     MiniportQueryOffload</a> function.


## -returns
None


## -remarks
An offload target calls 
    <b>NdisMQueryOffloadStateComplete</b> to complete a query operation that was initiated when NDIS called
    the 
    <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a> function of
    the offload target.

Before calling 
    <b>NdisMQueryOffloadStateComplete</b>, the offload target must:

Fill in each 
      <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570939">offload state structure</a> in the state
      tree with the current values of that structure's variables.

Write a status value of NDIS_STATUS_SUCCESS or NDIS_STATUS_FAILURE to the 
      <b>Status</b> member of each NDIS_MINIPORT_OFFLOAD_BLOCK_LIST structure in the state tree.


## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>
</dt>
<dt>
<a href="..\ndischimney\ns-ndischimney-_ndis_miniport_offload_block_list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMQueryOffloadStateComplete function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

