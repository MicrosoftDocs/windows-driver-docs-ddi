---
UID: NS:ntddndis._NDIS_TIMESTAMP_CAPABILITY_FLAGS
title: _NDIS_TIMESTAMP_CAPABILITY_FLAGS (ntddndis.h)
description: The NDIS_TIMESTAMP_CAPABILITY_FLAGS structure represents a network interface card (NIC)'s timestamping capabilities in various contexts.
tech.root: netvista
ms.date: 12/31/2020
keywords: ["NDIS_TIMESTAMP_CAPABILITY_FLAGS structure"]
ms.keywords: _NDIS_TIMESTAMP_CAPABILITY_FLAGS, NDIS_TIMESTAMP_CAPABILITY_FLAGS, *PNDIS_TIMESTAMP_CAPABILITY_FLAGS,
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
req.typenames: NDIS_TIMESTAMP_CAPABILITY_FLAGS, *PNDIS_TIMESTAMP_CAPABILITY_FLAGS
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _NDIS_TIMESTAMP_CAPABILITY_FLAGS
 - ntddndis/_NDIS_TIMESTAMP_CAPABILITY_FLAGS
 - PNDIS_TIMESTAMP_CAPABILITY_FLAGS
 - ntddndis/PNDIS_TIMESTAMP_CAPABILITY_FLAGS
 - NDIS_TIMESTAMP_CAPABILITY_FLAGS
 - ntddndis/NDIS_TIMESTAMP_CAPABILITY_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _NDIS_TIMESTAMP_CAPABILITY_FLAGS
 - PNDIS_TIMESTAMP_CAPABILITY_FLAGS
 - NDIS_TIMESTAMP_CAPABILITY_FLAGS
---

# _NDIS_TIMESTAMP_CAPABILITY_FLAGS structure

## -description

The **NDIS_TIMESTAMP_CAPABILITY_FLAGS** structure represents a network interface card (NIC)'s timestamping capabilities in various contexts.

## -struct-fields

### -field PtpV2OverUdpIPv4EventMsgReceiveHw

A value of **TRUE** indicates that during packet reception the NIC can recognize in hardware a PTP version 2 *event* message contained in an IPv4 UDP packet and generate a timestamp in hardware corresponding to when such a packet was received. A value of **FALSE** indicates the hardware is not capable of this.

### -field PtpV2OverUdpIPv4AllMsgReceiveHw

A value of **TRUE** indicates that during packet reception the NIC can recognize in hardware *any* PTP version 2 message (not just PTP event messages) contained in an IPv4 UDP packet and generate a timestamp in hardware corresponding to when such a packet was received. A value of **FALSE** indicates the hardware is not capable of this.

### -field PtpV2OverUdpIPv4EventMsgTransmitHw

A value of **TRUE** indicates that during packet transmission the NIC can recognize in hardware a PTP version 2 *event* message contained in an IPv4 UDP packet and generate a timestamp in hardware corresponding to when such a packet was transmitted. A value of **FALSE** indicates the hardware is not capable of this.

### -field PtpV2OverUdpIPv4AllMsgTransmitHw

A value of **TRUE** indicates that during packet transmission the NIC can recognize in hardware *any* PTP version 2 message (not just PTP event messages) contained in an IPv4 UDP packet and generate a timestamp in hardware corresponding to when such a packet was transmitted. A value of **FALSE** indicates the hardware is not capable of this.

### -field PtpV2OverUdpIPv6EventMsgReceiveHw

A value of **TRUE** indicates that during packet reception the NIC can recognize in hardware a PTP version 2 *event* message contained in an IPv6 UDP packet and generate a timestamp in hardware corresponding to when such a packet was received. A value of **FALSE** indicates the hardware is not capable of this.

### -field PtpV2OverUdpIPv6AllMsgReceiveHw

A value of **TRUE** indicates that during packet reception the NIC can recognize in hardware *any* PTP version 2 message (not just PTP event messages) contained in an IPv6 UDP packet and generate a timestamp in hardware corresponding to when such a packet was received. A value of **FALSE** indicates the hardware is not capable of this.

### -field PtpV2OverUdpIPv6EventMsgTransmitHw

A value of **TRUE** indicates that during packet transmission the NIC can recognize in hardware a PTP version 2 *event* message contained in an IPv6 UDP packet and generate a timestamp in hardware corresponding to when such a packet was transmitted. A value of **FALSE** indicates the hardware is not capable of this.

### -field PtpV2OverUdpIPv6AllMsgTransmitHw

A value of **TRUE** indicates that during packet transmission the NIC can recognize in hardware *any* PTP version 2 message (not just PTP event messages) contained in an IPv6 UDP packet and generate a timestamp in hardware corresponding to when such a packet was transmitted. A value of **FALSE** indicates the hardware is not capable of this

### -field AllReceiveHw

A value of **TRUE** indicates that the NIC can generate a hardware timestamp for all received packets (for example, not just PTP). A value of **FALSE** indicates the NIC doesn't have this capability.

### -field AllTransmitHw

A value of **TRUE** indicates that the NIC can generate a hardware timestamp for all transmitted packets (for example, not just PTP). A value of **FALSE** indicates the NIC doesn't have this capability.

### -field TaggedTransmitHw

A value of **TRUE** indicates that the NIC can generate a hardware timestamp for any specific transmitted packet when indicated to do so by the operating system. The operating system will indicate this to the miniport/hardware using a metadata field in the packet described further below in the section on Transmit side timestamping. A value of **FALSE** indicates the NIC doesn't have this capability.

### -field AllReceiveSw

A value of **TRUE** indicates that the miniport driver can generate a software timestamp for all received packets. The driver should generate the timestamp by calling the [**KeQueryPerformanceCounter**](../ntifs/nf-ntifs-kequeryperformancecounter.md) API. A value of **FALSE** indicates the NIC doesn't have this capability.

### -field AllTransmitSw

A value of **TRUE** indicates that the miniport driver can generate a software timestamp for all transmitted packets. The timestamp should be generated in software using [**KeQueryPerformanceCounter**](../ntifs/nf-ntifs-kequeryperformancecounter.md) just before the packet is transmitted. A value of **FALSE** indicates the NIC doesn't have this capability.

### -field TaggedTransmitSw

A value of **TRUE** indicates that the miniport driver can generate a software timestamp for any specific transmitted packet when indicated to do so by the operating system. The operating system will indicate this to the miniport using a metadata field in the packet described further below. The timestamp should be generated in software using [**KeQueryPerformanceCounter**](../ntifs/nf-ntifs-kequeryperformancecounter.md) just before the packet is transmitted. A value of **FALSE** indicates the NIC doesn't have this capability.

## -remarks

## -see-also

[**NDIS_TIMESTAMP_CAPABILITIES**](ns-ntddndis-_ndis_timestamp_capabilities.md)

[**KeQueryPerformanceCounter**](../ntifs/nf-ntifs-kequeryperformancecounter.md)