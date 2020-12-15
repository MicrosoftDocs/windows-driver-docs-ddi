---
UID: NS:ntddndis._NDIS_RSS_PROCESSOR
title: _NDIS_RSS_PROCESSOR (ntddndis.h)
description: The NDIS_RSS_PROCESSOR structure specifies information about a processor in the local computer for receive side scaling (RSS).
old-location: netvista\ndis_rss_processor.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_RSS_PROCESSOR structure"]
ms.keywords: "*PNDIS_RSS_PROCESSOR, NDIS_RSS_PROCESSOR, NDIS_RSS_PROCESSOR structure [Network Drivers Starting with Windows Vista], PNDIS_RSS_PROCESSOR, PNDIS_RSS_PROCESSOR structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RSS_PROCESSOR, ndis_processor_group_ref_cbab90a4-91cf-4df3-a9dc-94f3cacf2039.xml, netvista.ndis_rss_processor, ntddndis/NDIS_RSS_PROCESSOR, ntddndis/PNDIS_RSS_PROCESSOR"
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
req.typenames: NDIS_RSS_PROCESSOR, *PNDIS_RSS_PROCESSOR
f1_keywords:
 - _NDIS_RSS_PROCESSOR
 - ntddndis/_NDIS_RSS_PROCESSOR
 - PNDIS_RSS_PROCESSOR
 - ntddndis/PNDIS_RSS_PROCESSOR
 - NDIS_RSS_PROCESSOR
 - ntddndis/NDIS_RSS_PROCESSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_RSS_PROCESSOR
---

# _NDIS_RSS_PROCESSOR structure


## -description

The NDIS_RSS_PROCESSOR structure specifies information about a processor in the local computer for
  receive side scaling (RSS).

## -struct-fields

### -field ProcNum

The processor number that is assigned to the processor.

### -field PreferenceIndex

The preference rating of the processor, which is based on Non-Uniform Memory Access (NUMA) distance.
      A lower value for 
      <b>PreferenceIndex</b> indicates a smaller NUMA distance to the miniport
      driver.

When choosing between multiple processors, miniport drivers should select the processor with a lower      
      <b>PreferenceIndex</b> value. This results in less overhead for the driver.

### -field Reserved

Reserved for NDIS.

## -remarks

The NDIS_RSS_PROCESSOR structure is used in the 
    <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor_info">
    NDIS_RSS_PROCESSOR_INFO</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_rss_processor_info">NDIS_RSS_PROCESSOR_INFO</a>
