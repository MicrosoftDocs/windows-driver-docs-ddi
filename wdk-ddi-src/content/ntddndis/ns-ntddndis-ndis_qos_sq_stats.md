---
UID: NS:ntddndis._NDIS_QOS_SQ_STATS
title: NDIS_QOS_SQ_STATS
ms.date: 10/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_QOS_SQ_STATS structure is used by OID_QOS_OFFLOAD_SQ_STATS to query the stats of an NDIS QoS Scheduler Queue (SQ). 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddndis.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.85 and later.
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_QOS_SQ_STATS, *PNDIS_QOS_SQ_STATS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_QOS_SQ_STATS
 - PNDIS_QOS_SQ_STATS
 - NDIS_QOS_SQ_STATS
f1_keywords:
 - _NDIS_QOS_SQ_STATS
 - ntddndis/_NDIS_QOS_SQ_STATS
 - PNDIS_QOS_SQ_STATS
 - ntddndis/PNDIS_QOS_SQ_STATS
 - NDIS_QOS_SQ_STATS
 - ntddndis/NDIS_QOS_SQ_STATS
dev_langs:
 - c++
---

## -description

The **NDIS_QOS_SQ_STATS** structure is used by [OID_QOS_OFFLOAD_SQ_STATS](/windows-hardware/drivers/network/oid-qos-offload-sq-stats) to query the stats of an NDIS Quality of Service (QoS) Scheduler Queue (SQ).  

## -struct-fields

### -field Header

The type, revision, and size of the **NDIS_QOS_SQ_STATS** structure. This member is formatted as an [**NDIS_OBJECT_HEADER**](ns-ntddndis-_ndis_object_header.md) structure.

The miniport driver must set the **Type** member of **Header** to NDIS_OBJECT_TYPE_DEFAULT, the **Revision** member to NDIS_QOS_SQ_STATS_REVISION_1, and the **Size** member to NDIS_SIZEOF_QOS_SQ_STATS_REVISION_1.  

### -field Flags

Not used in NDIS_QOS_SQ_STATS_REVISION_1. The caller sets this field to **zero**.

### -field SqId

An NDIS_QOS_SQ_ID containing the SQ ID of the SQ. NDIS assigns this ID.

### -field SqType

An [**NDIS_QOS_SQ_TYPE**](ne-ntddndis-ndis_qos_sq_type.md) that contains the type of this SQ. This can be **NdisQSQosSqSQTypeStandard** from the enum definition of **NDIS_QOS_SQ_TYPE**.

### -field BytesTransmitted

An array of UINT64 elements, one for each traffic class (TC). Each element specifies the total number of bytes on that TC for this SQ that have been successfully transmitted.

### -field PktsTransmitted

An array of UINT64 elements, one for each traffic class. Each element specifies the total number of packets on that TC for this SQ that have been successfully transmitted.

## -remarks

If the query [OID_QOS_OFFLOAD_SQ_STATS](/windows-hardware/drivers/network/oid-qos-offload-sq-stats) OID contains a valid vPortID, then the returned stats are specific to the vPort specified on this SQ.

If the query OID does not contain a valid vPortID, then the returned stats specify the total stats across all vPorts associated with the SQ.

## -see-also

[OID_QOS_OFFLOAD_SQ_STATS](/windows-hardware/drivers/network/oid-qos-offload-sq-stats)

[**NDIS_QOS_SQ_TYPE**](ne-ntddndis-ndis_qos_sq_type.md)

[**NDIS_QOS_SQ_PARAMETERS_ENUM_ARRAY**](ns-ntddndis-ndis_qos_sq_parameters_enum_array.md)

[**NDIS_OBJECT_HEADER**](ns-ntddndis-_ndis_object_header.md)