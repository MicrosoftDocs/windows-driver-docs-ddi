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

The **NDIS_QOS_SQ_PARAMETERS** structure is used by [OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs) to enumerate the NDIS Quality of Service (QoS) Scheduler Queues (SQs) created on a NIC switch.

<!--
OID_QOS_OFFLOAD_ENUM_SQS 

Overlying drivers issue OID query requests of OID_QOS_OFFLOAD_ENUM_SQS to obtain a list of all SQs currently present on a miniport adapter and their parameters. 

After a successful return from the OID query request, the InformationBuffer member of the NDIS_OID_REQUEST structure contains a pointer to an NDIS_QOS_SQ_PARAMETERS_ARRAY structure. Each element of the array is an NDIS_QOS_SQ_PARAMETERS structure. 
-->

## -struct-fields

### -field Header

The type, revision, and size of the **NDIS_QOS_SQ_PARAMETERS** structure. This member is formatted as an [**NDIS_OBJECT_HEADER**](ns-ntddndis-_ndis_object_header.md) structure.

The miniport driver must set the **Type** member of **Header** to NDIS_OBJECT_TYPE_DEFAULT.

The driver must set the **Revision** member of **Header** to NDIS_QOS_SQ_PARAMETERS_REVISION_2.

The driver must set the **Size** member to NDIS_SIZEOF_QOS_SQ_PARAMETERS_REVISION_2.

### -field Flags

A ULONG value that contains a bitwise OR of flags. These flags specify the miscellaneous capabilities and attributes of the Hardware QoS Offload features that are enabled on the SQ. The following flags are defined:

#### NDIS_QOS_SQ_TRANSMIT_CAP_ENABLED

If this flag is set, transmit bandwidth caps are enabled on this SQ.

#### NDIS_QOS_SQ_TRANSMIT_RESERVATION_ENABLED

If this flag is set, transmit bandwidth reservations are enabled on this SQ. This flag is not set if the SQ type is NdisQSQosSqSQTypeGFT.

#### NDIS_QOS_SQ_RECEIVE_CAP_ENABLED

If this flag is set, receive bandwidth caps are enabled on this SQ.

### -field SQId

An NDIS_QOS_SQ_ID that contains the SQ ID of this SQ. NDIS assigns this ID.

### -field SQType

An **NDIS_QOS_SQ_TYPE** that contains the type of this SQ. This can be NdisQSQosSqSQTypeStandard from the enum definition of **NDIS_QOS_SQ_TYPE**.

### -field TcEnabledTable

An array of BOOLEAN values that specify whether each traffic class (from 0 to NDIS_QOS_MAXIMUM_TRAFFIC_CLASSES) is enabled for scheduling on this SQ.  

Any traffic class (TC) for which this field is **TRUE** should be read and validated in the tables below. TCs for which this field is **TRUE** are also rate limited by the **CrossTcTransmitBandwidthCap** rate limit.  

TCs for which this field is **FALSE** do not participate in any QoS rate limiting, either from **CrossTcTransmitBandwidthCap** or from one of the per-TC tables below.

### -field TcTransmitBandwidthCapTable

An array of ULONG values that specify transmit bandwidth caps for each TC, in Mbps. Elements are only valid if **TransmitCapEnabled** is **TRUE**(if the NDIS_QOS_SQ_TRANSMIT_CAP_ENABLED flag is set?), and only then for elements where **TcEnabledTable** is **TRUE**. An element with a value of 0 has no cap.

The NIC should queue any transmit packets on this SQ on a given TC if they exceed the rate specified in this table.

### -field TcTransmitBandwidthReservationTable

An array of ULONG values that specify transmit bandwidth reservations for each TC, in relative values from **0** – **ULONG_MAX**. Elements are only valid if **TransmitReservationEnabled** is **TRUE**(if the NDIS_QOS_SQ_TRANSMIT_RESERVATION_ENABLED flag is set?), and only then for elements where **TcEnabledTable** is **TRUE**. An element with a value of **0** means that transmit packets on this SQ/TC share the default SQ’s reservation for that TC.

The NIC should queue any transmit packets on this SQ on a given TC if other SQs on this TC require bandwidth to meet their reservation.

### -field TcReceiveBandwidthCapTable

### -field CrossTcTransmitBandwidthCap

### -field MaxNumSqInputs

## -remarks

The **NDIS_QOS_SQ_PARAMETERS** structure is returned in OID query request of [OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs).

## -see-also

[OID_QOS_OFFLOAD_ENUM_SQS](/windows-hardware/drivers/network/oid-qos-offload-enum-sqs)

[NDIS_QOS_SQ_PARAMETERS_ENUM_ARRAY](ns-ntddndis-ndis_qos_sq_parameters_enum_array.md)