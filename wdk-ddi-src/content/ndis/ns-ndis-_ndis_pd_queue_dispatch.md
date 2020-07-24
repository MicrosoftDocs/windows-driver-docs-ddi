---
UID: NS:ndis._NDIS_PD_QUEUE_DISPATCH
title: _NDIS_PD_QUEUE_DISPATCH (ndis.h)
description: This structure contains a provider's driver routines for receive or transmit queues.
old-location: netvista\ndis_pd_queue_dispatch.htm
tech.root: netvista
ms.assetid: F9738CF9-AAC8-413C-A890-D6FAD7EEFD54
ms.date: 05/02/2018
keywords: ["_NDIS_PD_QUEUE_DISPATCH structure"]
ms.keywords: NDIS_PD_QUEUE_DISPATCH, NDIS_PD_QUEUE_DISPATCH structure [Network Drivers Starting with Windows Vista], PNDIS_PD_QUEUE_DISPATCH, PNDIS_PD_QUEUE_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_QUEUE_DISPATCH, ndis/NDIS_PD_QUEUE_DISPATCH, ndis/PNDIS_PD_QUEUE_DISPATCH, netvista.ndis_pd_queue_dispatch
f1_keywords:
 - "ndis/NDIS_PD_QUEUE_DISPATCH"
 - "NDIS_PD_QUEUE_DISPATCH"
req.header: ndis.h
req.include-header: 
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- NDIS_PD_QUEUE_DISPATCH
targetos: Windows
req.typenames: NDIS_PD_QUEUE_DISPATCH
---

# _NDIS_PD_QUEUE_DISPATCH structure


## -description


This structure contains a provider's driver routines for receive or transmit queues.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_QUEUE_DISPATCH</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_QUEUE_DISPATCH_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_QUEUE_DISPATCH_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field PDPostAndDrainBufferList

A pointer to the provider's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_post_and_drain_buffer_list">PDPostAndDrainBufferList</a> routine.


### -field PDQueryQueueDepth

A pointer to the provider's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_query_queue_depth">PDQueryQueueDepth</a> routine.


### -field PDFlushQueue

A pointer to the provider's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_flush_queue">PDFlushQueue</a> routine.


### -field PDPostAndDrainBufferListEx

 



