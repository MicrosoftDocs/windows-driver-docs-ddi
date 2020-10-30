---
UID: NS:ntddndis._NDIS_QOS_OFFLOAD_CAPABILITIES
title: NDIS_QOS_OFFLOAD_CAPABILITIES
ms.date: 10/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_QOS_OFFLOAD_CAPABILITIES structure specifies the hardware and current Hardware Quality of Service (QoS) capabilities of a miniport adapter.
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
req.typenames: NDIS_QOS_OFFLOAD_CAPABILITIES, *PNDIS_QOS_OFFLOAD_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_QOS_OFFLOAD_CAPABILITIES
 - PNDIS_QOS_OFFLOAD_CAPABILITIES
 - NDIS_QOS_OFFLOAD_CAPABILITIES
f1_keywords:
 - _NDIS_QOS_OFFLOAD_CAPABILITIES
 - ntddndis/_NDIS_QOS_OFFLOAD_CAPABILITIES
 - PNDIS_QOS_OFFLOAD_CAPABILITIES
 - ntddndis/PNDIS_QOS_OFFLOAD_CAPABILITIES
 - NDIS_QOS_OFFLOAD_CAPABILITIES
 - ntddndis/NDIS_QOS_OFFLOAD_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **NDIS_QOS_OFFLOAD_CAPABILITIES** structure specifies the hardware and current Hardware Quality of Service (QoS) offload capabilities of a miniport adapter.

## -struct-fields

### -field Header

The type, revision, and size of the **NDIS_QOS_OFFLOAD_CAPABILITIES** structure. This member is formatted as an [**NDIS_OBJECT_HEADER**](ns-ntddndis-_ndis_object_header.md) structure.

The miniport driver must set the **Type** member of **Header** to NDIS_OBJECT_TYPE_DEFAULT.

The driver must set the **Revision** member of **Header** to NDIS_QOS_OFFLOAD_CAPABILITIES_REVISION_2 to specify the version of the **NDIS_QOS_OFFLOAD_CAPABILITIES** structure.

The driver must set the **Size** member to NDIS_SIZEOF_QOS_OFFLOAD_CAPABILITIES_REVISION_2.

### -field Flags

This field is not used in NDIS_QOS_OFFLOAD_CAPABILITIES_REVISION_2. The driver must set this member to **zero**.

### -field SupportedSqTypes

A ULONG value that contains a bitwise OR of flags. These flags specify the type of NDIS QoS Scheduler Queues (SQs) that the miniport adapter supports. The following flags are defined:

#### NDIS_QOS_OFFLOAD_CAPS_STANDARD_SQ

If this flag is set, the miniport adapter supports standard SQs.

### -field TransmitCapSupported

An array of BOOLEAN values that specify whether the miniport adapter supports transmit bandwidth caps for each traffic class (TC). For more information, see [NDIS QoS Traffic Classes](/windows-hardware/drivers/network/ndis-qos-traffic-classes).

### -field TransmitReservationSupported

An array of BOOLEAN values that specify whether the miniport adapter supports transmit bandwidth reservations for each TC.

### -field ReceiveCapSupported

An array of BOOLEAN values that specify whether the miniport adapter supports receive bandwidth caps for each TC.

### -field TransmitGftCapSupported

Reserved for future use.

### -field ReceiveGftCapSupported

Reserved for future use.

### -field TcSupportedTable

An array of BOOLEAN values that specify whether the miniport adapter supports rate limits for each TC.

### -field NumStandardSqsSupported

A ULONG value that contains the maximum number of standard SQs that can be created on the miniport adapter.

### -field NumGftSqsSupported

For forward compatibility, the miniport driver must set this field to **zero** when responding to the OS query.

### -field ReservationGranularitySupported

A ULONG value that contains the scheduling granularity that the NIC can support for transmit reservations. For example, if the NIC can support at most a 1:10000 ratio between effective queues, this value should be 10000. This value is purely informational. A NIC may be asked to schedule queues with ratios between reservation values that exceed this granularity. In this case, the result should be a best approximation.

### -field MaxNumSqInputs

A ULONG value that contains the maximum number of vPorts that can be associated with an SQ.

### -field CrossTcTransmitMaxCapSupported

If **TRUE**, the miniport adapter supports a single transmit cap value for traffics across multiple TCs.

## -remarks

The **NDIS_QOS_OFFLOAD_CAPABILITIES** structure is returned in OID query requests [OID_QOS_OFFLOAD_HARDWARE_CAPABILITIES](/windows-hardware/drivers/network/oid-qos-offload-hardware-capabilities) and [OID_QOS_OFFLOAD_CURRENT_CAPABILITIES](/windows-hardware/drivers/network/oid-qos-offload-current-capabilities).

## -see-also

[**NDIS_OBJECT_HEADER**](ns-ntddndis-_ndis_object_header.md)

[OID_QOS_OFFLOAD_HARDWARE_CAPABILITIES](/windows-hardware/drivers/network/oid-qos-offload-hardware-capabilities)

[OID_QOS_OFFLOAD_CURRENT_CAPABILITIES](/windows-hardware/drivers/network/oid-qos-offload-current-capabilities)

[NDIS QoS Traffic Classes](/windows-hardware/drivers/network/ndis-qos-traffic-classes)

