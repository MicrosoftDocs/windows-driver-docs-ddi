---
UID: NS:ndis._NDIS_PD_COUNTER_PARAMETERS
title: _NDIS_PD_COUNTER_PARAMETERS (ndis.h)
description: This structure holds parameters for the provider counter.
old-location: netvista\ndis_pd_counter_parameters.htm
tech.root: netvista
ms.assetid: 0F2AB5A3-9208-426A-ADC5-C1AD3BADFD83
ms.date: 05/02/2018
keywords: ["NDIS_PD_COUNTER_PARAMETERS structure"]
ms.keywords: NDIS_PD_COUNTER_PARAMETERS, NDIS_PD_COUNTER_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PD_COUNTER_PARAMETERS, PNDIS_PD_COUNTER_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PD_COUNTER_PARAMETERS, ndis/NDIS_PD_COUNTER_PARAMETERS, ndis/PNDIS_PD_COUNTER_PARAMETERS, netvista.ndis_pd_counter_parameters
f1_keywords:
 - "ndis/NDIS_PD_COUNTER_PARAMETERS"
 - "NDIS_PD_COUNTER_PARAMETERS"
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
- NDIS_PD_COUNTER_PARAMETERS
targetos: Windows
req.typenames: NDIS_PD_COUNTER_PARAMETERS
---

# _NDIS_PD_COUNTER_PARAMETERS structure


## -description


This structure holds parameters for the provider counter.


## -struct-fields




### -field Header

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the <b>NDIS_PD_COUNTER_PARAMETERS</b> structure. Set the members of this structure as follows:

<ul>
<li><b>Type</b> = <b>NDIS_OBJECT_TYPE_DEFAULT</b></li>
<li><b>Revision</b> = <b>NDIS_PD_COUNTER_PARAMETERS_REVISION_1</b></li>
<li><b>Size</b> = <b>NDIS_SIZEOF_PD_COUNTER_PARAMETERS_REVISION_1</b></li>
</ul>

### -field Flags

This member is reserved and must be set to 0.


### -field CounterName

This member  is ignored by the PD provider. It is used by the PD platform for publishing the counter to the Windows Performance Counter subsystem (so that the counter can be viewed using PerfMon and accessed by system APIs programmatically).


### -field Type

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-ndis_pd_counter_type">NDIS_PD_COUNTER_TYPE</a> enumeration value that specifies the counter type.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ne-ndis-ndis_pd_counter_type">NDIS_PD_COUNTER_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-ndis_pd_allocate_counter">NdisPDAllocateCounter</a>
 

 

