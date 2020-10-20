---
UID: NS:ntddndis._NDIS_QOS_SQ_PARAMETERS
title: NDIS_QOS_SQ_PARAMETERS
ms.date: 10/30/2020
ms.topic: language-reference
targetos: Windows
description: The **NDIS_QOS_SQ_PARAMETERS** structure is used by OID_QOS_OFFLOAD_ENUM_SQS to enumerate the NDIS QoS Scheduler Queues (SQs) created on a NIC switch.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddndis.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.84 and later.
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_QOS_SQ_PARAMETERS, *PNDIS_QOS_SQ_PARAMETERS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_QOS_SQ_PARAMETERS
 - PNDIS_QOS_SQ_PARAMETERS
 - NDIS_QOS_SQ_PARAMETERS
f1_keywords:
 - _NDIS_QOS_SQ_PARAMETERS
 - ntddndis/_NDIS_QOS_SQ_PARAMETERS
 - PNDIS_QOS_SQ_PARAMETERS
 - ntddndis/PNDIS_QOS_SQ_PARAMETERS
 - NDIS_QOS_SQ_PARAMETERS
 - ntddndis/NDIS_QOS_SQ_PARAMETERS
dev_langs:
 - c++
---

## -description

The **NDIS_QOS_SQ_PARAMETERS** structure is used by [OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs) to enumerate the NDIS QoS Scheduler Queues (SQs) created on a NIC switch.

<!--
OID_QOS_OFFLOAD_ENUM_SQS 

Overlying drivers issue OID query requests of OID_QOS_OFFLOAD_ENUM_SQS to obtain a list of all SQs currently present on a miniport adapter and their parameters. 

After a successful return from the OID query request, the InformationBuffer member of the NDIS_OID_REQUEST structure contains a pointer to an NDIS_QOS_SQ_PARAMETERS_ARRAY structure. Each element of the array is an NDIS_QOS_SQ_PARAMETERS structure. 
-->

## -struct-fields

### -field Header

### -field Flags

### -field SqId

### -field SqType

### -field TcEnabledTable

### -field TcTransmitBandwidthCapTable

### -field TcTransmitBandwidthReservationTable

### -field TcReceiveBandwidthCapTable

### -field CrossTcTransmitBandwidthCap

### -field MaxNumSqInputs

## -remarks

The **NDIS_QOS_SQ_PARAMETERS** structure is returned in OID query request of [OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs).

## -see-also

[OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs)

[NDIS_QOS_SQ_PARAMETERS_ENUM_ARRAY](ns-ntddndis-ndis_qos_sq_parameters_enum_array.md)