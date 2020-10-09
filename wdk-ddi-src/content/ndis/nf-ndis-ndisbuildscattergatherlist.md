---
UID: NF:ndis.NdisBuildScatterGatherList
title: NdisBuildScatterGatherList function (ndis.h)
description: The NdisBuildScatterGatherList function builds a scatter/gather list by using the specified parameters.
old-location: netvista\ndisbuildscattergatherlist.htm
tech.root: netvista
ms.assetid: 439d68ec-9d27-484b-b6a3-9bae732d142e
ms.date: 05/02/2018
keywords: ["NdisBuildScatterGatherList function"]
ms.keywords: NdisBuildScatterGatherList, NdisBuildScatterGatherList function [Network Drivers Starting with Windows Vista], ndis/NdisBuildScatterGatherList, ndis_shared_memory_ref_a0497f0f-75af-4813-81c9-544c02a7b372.xml, netvista.ndisbuildscattergatherlist
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: = DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisBuildScatterGatherList
 - ndis/NdisBuildScatterGatherList
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisBuildScatterGatherList
---

# NdisBuildScatterGatherList function


## -description

The 
  <b>NdisBuildScatterGatherList</b> function builds a scatter/gather list by using the specified
  parameters.

## -parameters

### -param NdisHandle 

[in]
An NDIS driver or instance handle that was obtained during caller initialization. For example, a
     miniport driver can use the NDIS handle that it obtained from the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> or 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>

### -param SGListParameters 

[in]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_scatter_gather_list_parameters">
     NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure that specifies the parameters for allocating the
     scatter/gather list.

## -returns

<b>NdisBuildScatterGatherList</b> can return the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>
</td>
<td width="60%">
The operation failed because the buffer length that is specified in the 
       <b>ScatterGatherListBufferSize</b> member of the 
       <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_scatter_gather_list_parameters">
       NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure was too short. In this case, NDIS provided the
       required buffer size in the 
       <b>ScatterGatherListBufferSizeNeeded</b> member.

</td>
</tr>
</table>

## -remarks

NDIS drivers call the 
    <b>NdisBuildScatterGatherList</b> function to build a scatter/gather list for a buffer. To call this
    function, a miniport driver specifies a miniport adapter handle or a protocol driver specifies an NDIS
    binding handle.

The underlying miniport adapter must have called 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
    NdisMRegisterScatterGatherDma</a> before a driver can call 
    <b>NdisBuildScatterGatherList</b>.

NDIS calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_process_sg_list">NetProcessSGList</a> function that is
    specified at the 
    <b>ProcessSGListHandler</b> member of the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_scatter_gather_list_parameters">
    NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure within the context of 
    <b>NdisBuildScatterGatherList</b>.

The drivers must call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfreescattergatherlist">
    NdisFreeScatterGatherList</a> function to free a scatter/gather list that was created with the 
    <b>
    NdisBuildScatterGatherList</b> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_scatter_gather_list_parameters">
   NDIS_SCATTER_GATHER_LIST_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterscattergatherdma">
   NdisMRegisterScatterGatherDma</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisregisterprotocoldriver">NdisRegisterProtocolDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_process_sg_list">NetProcessSGList</a>