---
UID: NS:ntddndis._NDIS_PROCESSOR_INFO_EX
title: _NDIS_PROCESSOR_INFO_EX (ntddndis.h)
description: The NDIS_PROCESSOR_INFO_EX structure specifies information about a processor in the local computer.
old-location: netvista\ndis_processor_info_ex.htm
tech.root: netvista
ms.assetid: e4f28f30-32bc-4bbc-8e95-f87dfe80229d
ms.date: 05/02/2018
keywords: ["NDIS_PROCESSOR_INFO_EX structure"]
ms.keywords: "*PNDIS_PROCESSOR_INFO_EX, NDIS_PROCESSOR_INFO_EX, NDIS_PROCESSOR_INFO_EX structure [Network Drivers Starting with Windows Vista], PNDIS_PROCESSOR_INFO_EX, PNDIS_PROCESSOR_INFO_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROCESSOR_INFO_EX, ndis_processor_group_ref_0a75adfb-c28f-4d9b-8b29-6da14662bda7.xml, netvista.ndis_processor_info_ex, ntddndis/NDIS_PROCESSOR_INFO_EX, ntddndis/PNDIS_PROCESSOR_INFO_EX"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: NDIS_PROCESSOR_INFO_EX, *PNDIS_PROCESSOR_INFO_EX
f1_keywords:
 - _NDIS_PROCESSOR_INFO_EX
 - ntddndis/_NDIS_PROCESSOR_INFO_EX
 - PNDIS_PROCESSOR_INFO_EX
 - ntddndis/PNDIS_PROCESSOR_INFO_EX
 - NDIS_PROCESSOR_INFO_EX
 - ntddndis/NDIS_PROCESSOR_INFO_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_PROCESSOR_INFO_EX
---

# _NDIS_PROCESSOR_INFO_EX structure


## -description

The <b>NDIS_PROCESSOR_INFO_EX</b> structure specifies information about a processor in the local
  computer.

## -struct-fields

### -field ProcNum

The processor number that is assigned to the processor.

### -field SocketId

The socket identifier for the processor. This is the number that is assigned to the motherboard
     socket on the local computer. That is, it is a physical processor identifier. The possible values for
     this member are zero to the number of sockets on the motherboard minus one.

### -field CoreId

The core ID of the processor. The value is in the range from zero through the number in the 
     <b>NumCoresPerSocket</b> member of the NDIS_SYSTEM_PROCESSOR_INFO_EX structure minus one.

### -field HyperThreadId

The hyper-threading ID of the processor. The value is in the range from zero through the number in
     the 
     <b>MaxHyperThreadingProcsPerCore</b> member of the NDIS_SYSTEM_PROCESSOR_INFO_EX structure minus
     one.

### -field NodeId

The node identifier of the processor. This is the number of the NUMA node to which the processor
     belongs. This range of possible values is zero to the number of NUMA nodes on the local computer minus
     one.

### -field NodeDistance

The node distance of the processor. If the handle at the 
     <i>NdisHandle</i> parameter that the caller passed to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetprocessorinformationex">
     NdisGetProcessorInformationEx</a> function is not <b>NULL</b> and is a miniport adapter handle, this member
     contains the distance of the corresponding NIC from this processor's NUMA node. Otherwise, this member
     is zero for miniport drivers or USHORT_MAX (0xffff) for other drivers.

## -remarks

The NDIS_PROCESSOR_INFO_EX structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_system_processor_info_ex">
    NDIS_SYSTEM_PROCESSOR_INFO_EX</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_processor_info">NDIS_PROCESSOR_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_system_processor_info_ex">NDIS_SYSTEM_PROCESSOR_INFO_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetprocessorinformationex">
   NdisGetProcessorInformationEx</a>

