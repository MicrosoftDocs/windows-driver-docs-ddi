---
UID: NF:ndis.NdisGetRssProcessorInformation
title: NdisGetRssProcessorInformation function (ndis.h)
description: The NdisGetRssProcessorInformation function retrieves information about the set of processors that a miniport driver must use for receive side scaling (RSS).
old-location: netvista\ndisgetrssprocessorinformation.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisGetRssProcessorInformation function"]
ms.keywords: NdisGetRssProcessorInformation, NdisGetRssProcessorInformation function [Network Drivers Starting with Windows Vista], ndis/NdisGetRssProcessorInformation, ndis_processor_group_ref_167a091b-01dd-4e5d-bee8-01f5aa9f56fd.xml, netvista.ndisgetrssprocessorinformation
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisGetRssProcessorInformation
 - ndis/NdisGetRssProcessorInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisGetRssProcessorInformation
---

# NdisGetRssProcessorInformation function


## -description

The 
  <b>NdisGetRssProcessorInformation</b> function retrieves information about the set of processors that a
  miniport driver must use for receive side scaling (RSS).

## -parameters

### -param NdisHandle 

[in]
An NDIS instance handle that was obtained during caller initialization. NDIS drivers can use the
     handles from the following functions:
     


<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>

### -param RssProcessorInfo 

[out, optional]
A pointer to a caller-allocated buffer where NDIS puts the 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor_info">NDIS_RSS_PROCESSOR_INFO</a> structure
     and an array of 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor">NDIS_RSS_PROCESSOR</a> structures that
     contain information about the RSS processor set. The caller provides the length of the buffer in the 
     <i>Size</i> parameter.

### -param Size 

[in, out]
A pointer to a value that is the size, in bytes, of the buffer that the caller provided. When the
     function returns, this member contains either the amount of data that NDIS put in the buffer or the
     required size of the buffer if the buffer was too short.

## -returns

<b>NdisGetRssProcessorInformation</b> can return one of the following status values:

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
The size that was specified in 
       <i>Size</i> parameter was too small. In this case, NDIS provides the required buffer size in the 
       <i>Size</i> parameter.

</td>
</tr>
</table>

## -remarks

NDIS drivers call the 
    <b>NdisGetRssProcessorInformation</b> function to retrieve information about the receive side scaling
    (RSS) processors on the local computer.

RSS-capable miniport drivers that support MSI-X call 
    <b>NdisGetRssProcessorInformation</b> in their 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
    MiniportFilterResourceRequirements</a> function. Miniport drivers set the interrupt affinity of the
    allocated MSI-X messages to the RSS processors that are specified in the 
    <b>RssProcessors</b> member of the 
    <i>RssProcessorInfo</i> parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pnp_irp">
   MiniportFilterResourceRequirements</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor">NDIS_RSS_PROCESSOR</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor_info">NDIS_RSS_PROCESSOR_INFO</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>
