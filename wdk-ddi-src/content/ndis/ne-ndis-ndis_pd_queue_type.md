---
UID: NE:ndis.NDIS_PD_QUEUE_TYPE
title: NDIS_PD_QUEUE_TYPE (ndis.h)
description: The NDIS_PD_QUEUE_TYPE enumeration defines types of PacketDirect Provider Interface (PDPI) queues. Its enumeration values are used in the QueueType member of the NDIS_PD_QUEUE_PARAMETERS structure.
old-location: netvista\ndis_pd_queue_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_PD_QUEUE_TYPE enumeration"]
ms.keywords: NDIS_PD_QUEUE_TYPE, NDIS_PD_QUEUE_TYPE enumeration [Network Drivers Starting with Windows Vista], PDQueueTypeMax, PDQueueTypeReceive, PDQueueTypeTransmit, PDQueueTypeUnknown, ndis/NDIS_PD_QUEUE_TYPE, ndis/PDQueueTypeMax, ndis/PDQueueTypeReceive, ndis/PDQueueTypeTransmit, ndis/PDQueueTypeUnknown, netvista.ndis_pd_queue_type
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
req.typenames: NDIS_PD_QUEUE_TYPE
f1_keywords:
 - NDIS_PD_QUEUE_TYPE
 - ndis/NDIS_PD_QUEUE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ndis.h
api_name:
 - NDIS_PD_QUEUE_TYPE
---

# NDIS_PD_QUEUE_TYPE enumeration


## -description

The <b>NDIS_PD_QUEUE_TYPE</b> enumeration defines types of PacketDirect Provider Interface (PDPI)  queues. Its enumeration values are used in the <b>QueueType</b> member of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_pd_queue_parameters">NDIS_PD_QUEUE_PARAMETERS</a> structure.

## -enum-fields

### -field PDQueueTypeUnknown

The queue type is not known.

### -field PDQueueTypeReceive

The queue is a receive queue.

### -field PDQueueTypeTransmit

The queue is a transmit queue.

### -field PDQueueTypeMax

The maximum value for this enumeration. This value might change in future versions of NDIS header files and binaries.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_pd_queue_parameters">NDIS_PD_QUEUE_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_allocate_queue">NdisPDAllocateQueue</a>

