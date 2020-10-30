---
UID: NS:ntddndis._NDIS_QOS_SQ_PARAMETERS_ENUM_ARRAY
title: NDIS_QOS_SQ_ARRAY
ms.date: 10/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_QOS_SQ_ARRAY structure is used to enumerate NDIS Quality of Service (QoS) Scheduler Queues (SQs) for parameters and stats.
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
req.typenames: NDIS_QOS_SQ_PARAMETERS_ENUM_ARRAY, *PNDIS_QOS_SQ_PARAMETERS_ENUM_ARRAY, NDIS_QOS_SQ_ARRAY, *PNDIS_QOS_SQ_ARRAY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_QOS_SQ_ARRAY
 - PNDIS_QOS_SQ_ARRAY
 - NDIS_QOS_SQ_ARRAY
f1_keywords:
 - _NDIS_QOS_SQ_ARRAY
 - ntddndis/_NDIS_QOS_SQ_ARRAY
 - PNDIS_QOS_SQ_ARRAY
 - ntddndis/PNDIS_QOS_SQ_ARRAY
 - NDIS_QOS_SQ_ARRAY
 - ntddndis/NDIS_QOS_SQ_ARRAY
dev_langs:
 - c++
---

## -description

The **NDIS_QOS_SQ_ARRAY** structure is used to enumerate NDIS Quality of Service (QoS) Scheduler Queues (SQs) for parameters and stats. This structure is returned in the OID query requests [OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs) and [OID_QOS_OFFLOAD_SQ_STATS](/windows-hardware/drivers/network/oid-qos-offload-sq-stats).

## Syntax

```cpp
typedef struct _NDIS_QOS_SQ_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  NDIS_QOS_SQ_TYPE   SqType;
  NDIS_QOS_SQ_ID     FirstSqId;
  ULONG              MaxSqsToReturn;
  ULONG              SqArrayOffset;
  ULONG              SqArrayNumElements;
  ULONG              SqArrayElementSize;
} NDIS_QOS_SQ_ARRAY, *PNDIS_QOS_SQ_ARRAY;
```

## -struct-fields

### -field Header

The type, revision, and size of the **NDIS_QOS_SQ_STATS** structure. This member is formatted as an [**NDIS_OBJECT_HEADER**](ns-ntddndis-_ndis_object_header.md) structure.

The miniport driver must set the **Type** member of **Header** to NDIS_OBJECT_TYPE_DEFAULT, the **Revision** member to NDIS_QOS_SQ_PARAMETERS_ARRAY_REVISION_1, and the **Size** member to NDIS_SIZEOF_QOS_SQ_PARAMETERS_ARRAY_REVISION_1.

### -field Flags

Not used in NDIS_QOS_SQ_PARAMETERS_ARRAY_REVISION_1. The caller sets this field to **zero**.

### -field SqType

An [**NDIS_QOS_SQ_TYPE**](ne-ntddndis-ndis_qos_sq_type.md) that contains the type of this SQ. This can be **NdisQSQosSqSQTypeStandard** from the enum definition of **NDIS_QOS_SQ_TYPE**.

### -field FirstSqId

An NDIS_QOS_SQ_ID that specifies the first SQ ID of this array.

### -field MaxSqsToReturn

The maximum number of SQs contained in this array.

### -field SqArrayOffset

The byte offset from the beginning of this structure that marks the beginning of an array. The type of each element depends on the OID request:

|OID   |Element type   |
|----------|-----------|
|[OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs)     |[**NDIS_QOS_SQ_PARAMETERS**](ns-ntddndis-ndis_qos_sq_parameters.md)       |
|[OID_QOS_OFFLOAD_SQ_STATS](/windows-hardware/drivers/network/oid-qos-offload-sq-stats)|[**NDIS_QOS_SQ_STATS**](ns-ntddndis-ndis_qos_sq_stats.md)   |

### -field SqArrayNumElements

The number of elements in this array specified by **SQArrayOffset**.

### -field SqArrayElementSize

The size of each element in this array.  

## -remarks

**NDIS_QOS_SQ_ARRAY** is returned in the OID query request [OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs), which enumerates the SQs created on a NIC switch 

**NDIS_QOS_SQ_ARRAY** is also returned in the OID query request [OID_QOS_OFFLOAD_SQ_STATS](/windows-hardware/drivers/network/oid-qos-offload-sq-stats), used to obtain a list of SQs currently present on a miniport adapter and their stat counters.

## -see-also

[OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs)

[OID_QOS_OFFLOAD_SQ_STATS](/windows-hardware/drivers/network/oid-qos-offload-sq-stats)

[**NDIS_QOS_SQ_STATS**](ns-ntddndis-ndis_qos_sq_stats.md)

[**NDIS_QOS_SQ_TYPE**](ne-ntddndis-ndis_qos_sq_type.md)

[**NDIS_QOS_SQ_PARAMETERS**](ns-ntddndis-ndis_qos_sq_parameters.md)

[**NDIS_OBJECT_HEADER**](ns-ntddndis-_ndis_object_header.md)