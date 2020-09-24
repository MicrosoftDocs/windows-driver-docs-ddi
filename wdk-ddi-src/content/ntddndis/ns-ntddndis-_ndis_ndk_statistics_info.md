---
UID: NS:ntddndis._NDIS_NDK_STATISTICS_INFO
title: _NDIS_NDK_STATISTICS_INFO (ntddndis.h)
description: The NDIS_NDK_STATISTICS_INFO structure contains the NDK statistics.
old-location: netvista\ndis_ndk_statistics_info.htm
tech.root: netvista
ms.assetid: F3FA3790-0754-4D5E-9F27-8ECD71278520
ms.date: 05/02/2018
keywords: ["NDIS_NDK_STATISTICS_INFO structure"]
ms.keywords: NDIS_NDK_STATISTICS_INFO, NDIS_NDK_STATISTICS_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NDK_STATISTICS_INFO, PNDIS_NDK_STATISTICS_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NDK_STATISTICS_INFO, netvista.ndis_ndk_statistics_info, ntddndis/NDIS_NDK_STATISTICS_INFO, ntddndis/PNDIS_NDK_STATISTICS_INFO
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.typenames: NDIS_NDK_STATISTICS_INFO
f1_keywords:
 - _NDIS_NDK_STATISTICS_INFO
 - ntddndis/_NDIS_NDK_STATISTICS_INFO
 - NDIS_NDK_STATISTICS_INFO
 - ntddndis/NDIS_NDK_STATISTICS_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_NDK_STATISTICS_INFO
---

# _NDIS_NDK_STATISTICS_INFO structure


## -description

The <b>NDIS_NDK_STATISTICS_INFO</b> structure contains the NDK statistics.

## -struct-fields

### -field Header

An <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure that describes this <b>NDIS_NDK_STATISTICS_INFO</b> structure. Set the members of the <b>NDIS_OBJECT_HEADER</b> structure as follows:

<ul>
<li>Set the <b>Type</b> member to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.</li>
<li>Set the <b>Revision</b> member to <b>NDIS_NDK_STATISTICS_INFO_REVISION_1</b>.</li>
<li>Set the <b>Size</b> member to <b>NDIS_SIZEOF_NDK_STATISTICS_INFO_REVISION_1</b>.</li>
</ul>

### -field Flags

### -field CounterSet

An <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_performance_counters">NDIS_NDK_PERFORMANCE_COUNTERS</a> structure that contains the NDK performance counters.

## -remarks

The <b>NDIS_NDK_STATISTICS_INFO</b> structure is returned with the <a href="/windows-hardware/drivers/network/oid-ndk-statistics">OID_NDK_STATISTICS</a> OID. The <b>InformationBuffer</b> member of the <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure contains a pointer to this structure.



The NDK-capable miniport driver is required to fill in the <b>CounterSet</b> member, which is an <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_performance_counters">NDIS_NDK_PERFORMANCE_COUNTERS</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_performance_counters">NDIS_NDK_PERFORMANCE_COUNTERS</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/oid-ndk-statistics">OID_NDK_STATISTICS</a>