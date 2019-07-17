---
UID: NE:ndis.__unnamed_enum_1
title: NDIS_PD_COUNTER_TYPE (ndis.h)
description: The NDIS_PD_COUNTER_TYPE enumeration defines types of PacketDirect Provider Interface (PDPI) counters. Its enumeration values are used in the Type member of the NDIS_PD_COUNTER_PARAMETERS structure.
old-location: netvista\ndis_pd_counter_type.htm
tech.root: netvista
ms.assetid: 36DA5A61-2DA4-4CD1-8BA5-74444DC002F0
ms.date: 05/02/2018
ms.keywords: NDIS_PD_COUNTER_TYPE, NDIS_PD_COUNTER_TYPE enumeration [Network Drivers Starting with Windows Vista], PDCounterTypeMax, PDCounterTypeReceiveFilter, PDCounterTypeReceiveQueue, PDCounterTypeTransmitQueue, PDCounterTypeUnknown, ndis/NDIS_PD_COUNTER_TYPE, ndis/PDCounterTypeMax, ndis/PDCounterTypeReceiveFilter, ndis/PDCounterTypeReceiveQueue, ndis/PDCounterTypeTransmitQueue, ndis/PDCounterTypeUnknown, netvista.ndis_pd_counter_type
ms.topic: enum
f1_keywords:
 - "ndis/NDIS_PD_COUNTER_TYPE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- NDIS_PD_COUNTER_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_PD_COUNTER_TYPE
---

# NDIS_PD_COUNTER_TYPE enumeration


## -description


The <b>NDIS_PD_COUNTER_TYPE</b> enumeration defines types of PacketDirect Provider Interface (PDPI)  counters. Its enumeration values are used in the <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_pd_counter_parameters">NDIS_PD_COUNTER_PARAMETERS</a> structure.


## -enum-fields




### -field PDCounterTypeUnknown

The counter type is not known.


### -field PDCounterTypeReceiveQueue

The counter is a receive queue counter.


### -field PDCounterTypeTransmitQueue

The counter is a transmit queue counter.


### -field PDCounterTypeReceiveFilter

The counter is a receive filter counter.


### -field PDCounterTypeMax

The maximum value for this enumeration. This value might change in future versions of NDIS header files and binaries.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_pd_counter_parameters">NDIS_PD_COUNTER_PARAMETERS</a>
 

 

