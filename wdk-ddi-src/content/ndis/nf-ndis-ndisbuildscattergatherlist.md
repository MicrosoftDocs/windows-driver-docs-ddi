---
UID: NF:ndis.NdisBuildScatterGatherList
title: NdisBuildScatterGatherList function
author: windows-driver-content
description: The NdisBuildScatterGatherList function builds a scatter/gather list by using the specified parameters.
old-location: netvista\ndisbuildscattergatherlist.htm
old-project: netvista
ms.assetid: 439d68ec-9d27-484b-b6a3-9bae732d142e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisBuildScatterGatherList, NdisBuildScatterGatherList, NdisBuildScatterGatherList function [Network Drivers Starting with Windows Vista], ndis_shared_memory_ref_a0497f0f-75af-4813-81c9-544c02a7b372.xml, netvista.ndisbuildscattergatherlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisBuildScatterGatherList
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisBuildScatterGatherList function


## -description


The 
  <b>NdisBuildScatterGatherList</b> function builds a scatter/gather list by using the specified
  parameters.


## -syntax


````
NDIS_STATUS NdisBuildScatterGatherList(
  _In_ NDIS_HANDLE                          NdisHandle,
  _In_ PNDIS_SCATTER_GATHER_LIST_PARAMETERS SGListParameters
);
````


## -parameters




### -param NdisHandle [in]

An NDIS driver or instance handle that was obtained during caller initialization. For example, a
     miniport driver can use the NDIS handle that it obtained from the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> or 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.
     Other NDIS drivers can use the handles from the following functions:
     


<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



### -param SGListParameters [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_scatter_gather_list_parameters.md">
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
       <a href="..\ndis\ns-ndis-_ndis_scatter_gather_list_parameters.md">
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
    <a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
    NdisMRegisterScatterGatherDma</a> before a driver can call 
    <b>NdisBuildScatterGatherList</b>.

NDIS calls the 
    <a href="..\ndis\nc-ndis-ndis_process_sg_list.md">NetProcessSGList</a> function that is
    specified at the 
    <b>ProcessSGListHandler</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_scatter_gather_list_parameters.md">
    NDIS_SCATTER_GATHER_LIST_PARAMETERS</a> structure within the context of 
    <b>NdisBuildScatterGatherList</b>.

The drivers must call the 
    <a href="..\ndis\nf-ndis-ndisfreescattergatherlist.md">
    NdisFreeScatterGatherList</a> function to free a scatter/gather list that was created with the 
    <b>
    NdisBuildScatterGatherList</b> function.




## -see-also

<a href="..\ndis\ns-ndis-_ndis_scatter_gather_list_parameters.md">
   NDIS_SCATTER_GATHER_LIST_PARAMETERS</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nc-ndis-ndis_process_sg_list.md">NetProcessSGList</a>



<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>



<a href="..\ndis\nf-ndis-ndismregisterscattergatherdma.md">
   NdisMRegisterScatterGatherDma</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisBuildScatterGatherList function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

