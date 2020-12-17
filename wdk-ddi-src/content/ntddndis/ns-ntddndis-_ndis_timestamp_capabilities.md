---
UID: NS:ntddndis._NDIS_TIMESTAMP_CAPABILITIES
title: _NDIS_TIMESTAMP_CAPABILITIES (ntddndis.h)
description: The NDIS_TIMESTAMP_CAPABILITIES structure describes a network interface card (NIC)'s timestamping capabilities.
tech.root: netvista
ms.date: 12/31/2020
keywords: ["NDIS_TIMESTAMP_CAPABILITIES structure"]
ms.keywords: _NDIS_TIMESTAMP_CAPABILITIES, NDIS_TIMESTAMP_CAPABILITIES, *PNDIS_TIMESTAMP_CAPABILITIES,
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 21H1. Supported in NDIS 6.82 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NDIS_TIMESTAMP_CAPABILITIES, *PNDIS_TIMESTAMP_CAPABILITIES
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_TIMESTAMP_CAPABILITIES
 - ntddndis/_NDIS_TIMESTAMP_CAPABILITIES
 - PNDIS_TIMESTAMP_CAPABILITIES
 - ntddndis/PNDIS_TIMESTAMP_CAPABILITIES
 - NDIS_TIMESTAMP_CAPABILITIES
 - ntddndis/NDIS_TIMESTAMP_CAPABILITIES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_TIMESTAMP_CAPABILITIES
---

# _NDIS_TIMESTAMP_CAPABILITIES structure


## -description

The **NDIS_TIMESTAMP_CAPABILITIES** structure describes a network interface card (NIC)'s timestamping capabilities.

## -struct-fields

### -field Header

The [NDIS_OBJECT_HEADER](../objectheader/ns-objectheader-ndis_object_header.md) structure that describes this **NDIS_TIMESTAMP_CAPABILITIES** structure. Set the members of the **NDIS_OBJECT_HEADER** structure as follows:

* Set the **Type** member to **NDIS_OBJECT_TYPE_DEFAULT**.

* Set the **Revision** member to **NDIS_TIMESTAMP_CAPABILITIES_REVISION_1**.

* Set the **Size** member to **NDIS_SIZEOF_TIMESTAMP_CAPABILITIES_REVISION_1**.


### -field HardwareClockFrequencyHz

This field contains the nominal frequency of the hardware clock used by the NIC for timestamping, rounded off to the nearest integer in Hertz units.

### -field CrossTimestamp

A value of **TRUE** indicates that the miniport/hardware combination is capable of generating a hardware cross timestamp by handling the [OID_TIMESTAMP_GET_CROSSTIMESTAMP](/windows-hardware/drivers/network/oid-timestamp-get-crosstimestamp) OID to generate a cross timestamp. A cross timestamp refers to a set of NIC hardware timestamp and system timestamp(s) obtained very close to each other. How these timestamps are obtained is described in more detail further down in the document. A value of **FALSE** indicates this capability does not exist.

### -field Reserved1

Reserved for future use.

### -field Reserved2

Reserved for future use.

### -field TimestampFlags

An [**NDIS_TIMESTAMP_CAPABILITY_FLAGS**](ns-ntddndis-_ndis_timestamp_capability_flags.md) structure that represents the NIC's timestamping capabilities in various contexts.

## -remarks

## -see-also

[**NDIS_TIMESTAMP_CAPABILITY_FLAGS**](ns-ntddndis-_ndis_timestamp_capability_flags.md)
