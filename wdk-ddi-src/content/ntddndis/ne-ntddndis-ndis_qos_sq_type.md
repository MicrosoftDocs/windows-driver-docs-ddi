---
UID: NE:ntddndis._NDIS_QOS_SQ_TYPE
title: NDIS_QOS_SQ_TYPE
ms.date: 10/30/2020
ms.topic: language-reference
targetos: Windows
description: The **NDIS_QOS_SQ_TYPE** enumeration specifies the type of an NDIS Quality of Service (QoS) Scheduler Queue (SQ).
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntddndis.h
req.include-header: ndis.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Supported in NDIS 6.85 and later.
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_QOS_SQ_TYPE
 - PNDIS_QOS_SQ_TYPE
 - NDIS_QOS_SQ_TYPE
f1_keywords:
 - _NDIS_QOS_SQ_TYPE
 - ntddndis/_NDIS_QOS_SQ_TYPE
 - PNDIS_QOS_SQ_TYPE
 - ntddndis/PNDIS_QOS_SQ_TYPE
 - NDIS_QOS_SQ_TYPE
 - ntddndis/NDIS_QOS_SQ_TYPE
dev_langs:
 - c++
---

## -description

The **NDIS_QOS_SQ_TYPE** enumeration specifies the type of an NDIS Quality of Service (QoS) Scheduler Queue (SQ).

## -enum-fields

The following SQ types are defined:

### -field NdisQosSqTypeUndefined

An undefined SQ type used for validation in code.

### -field NdisQosSqTypeStandard

A standard (non-GFT) SQ.

### -field NdisQosSqTypeGFT

Not currently in use.

### -field NdisQosSqTypeMax

Used for validation in code.

## -remarks

The **NDIS_QOS_SQ_TYPE** enumeration is a member of the [**NDIS_QOS_SQ_PARAMETERS**](ns-ntddndis-ndis_qos_sq_parameters.md), [**NDIS_QOS_SQ_ARRAY**](ns-ntddndis-ndis_qos_sq_parameters_enum_array.md), and [**NDIS_QOS_SQ_STATS**](ns-ntddndis-ndis_qos_sq_stats.md) structures.

## -see-also

[**NDIS_QOS_SQ_PARAMETERS**](ns-ntddndis-ndis_qos_sq_parameters.md)

[**NDIS_QOS_SQ_ARRAY**](ns-ntddndis-ndis_qos_sq_parameters_enum_array.md)

[**NDIS_QOS_SQ_STATS**](ns-ntddndis-ndis_qos_sq_stats.md)

[**NDIS_QOS_OFFLOAD_CAPABILITIES**](ns-ntddndis-ndis_qos_offload_capabilities.md)
