---
UID: NS:netadapter._NET_ADAPTER_WAKE_REASON_PACKET
title: NET_ADAPTER_WAKE_REASON_PACKET (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_WAKE_REASON_PACKET structure describes a network packet (known as a wake packet) that caused the network adapter to generate a wake-up event.
tech.root: netvista
ms.assetid: b6693c4b-f299-4437-953c-868e6238c9b2
ms.author: windowsdriverdev
ms.date: 10/25/2019
keywords: ["NET_ADAPTER_WAKE_REASON_PACKET structure"]
ms.keywords: NET_ADAPTER_WAKE_REASON_PACKET, NET_ADAPTER_WAKE_REASON_PACKET,
req.header: netadaptercx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_ADAPTER_WAKE_REASON_PACKET
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_ADAPTER_WAKE_REASON_PACKET
 - netadapter/_NET_ADAPTER_WAKE_REASON_PACKET
 - NET_ADAPTER_WAKE_REASON_PACKET
 - netadapter/NET_ADAPTER_WAKE_REASON_PACKET
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_WAKE_REASON_PACKET
product:
 - Windows
---

# NET_ADAPTER_WAKE_REASON_PACKET structure


## -description

The **NET_ADAPTER_WAKE_REASON_PACKET** structure describes a network packet (known as a wake packet) that caused the network adapter to generate a wake-up event.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field PatternId

A ULONG value that specifies the identifier of the wake-on-LAN (WOL) pattern that matches the wake packet.

### -field OriginalPacketSize

A ULONG value that specifies the original length, in units of bytes, of the wake packet.

### -field WakePacket

 
A WDFMEMORY buffer that contains the wake packet.

## -remarks

Call [**NET_ADAPTER_WAKE_REASON_PACKET_INIT**](nf-netadapter-net_adapter_wake_reason_packet_init.md) to initialize this structure if the [**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md) is NetWakeSourceTypeBitmapPattern.

Call [**NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT**](nf-netadapter-net_adapter_wake_reason_magic_packet_init.md) to initialize this structure if the **NET_WAKE_SOURCE_TYPE** is NetWakeSourceTypeMagicPacket.

Call [**NET_ADAPTER_WAKE_REASON_FILTER_PACKET_INIT**](nf-netadapter-net_adapter_wake_reason_filter_packet_init.md) to initialize this structure if the **NET_WAKE_SOURCE_TYPE** is NetWakeSourceTypePacketFilterMatch.

A **NET_ADAPTER_WAKE_REASON_PACKET** structure is passed as an input parameter to [**NetAdapterReportWakeReasonPacket**](../netadapter/nf-netadapter-netadapterreportwakereasonpacket.md).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_REASON_PACKET_INIT**](../netadapter/nf-netadapter-net_adapter_wake_reason_packet_init.md)

[**NetAdapterReportWakeReasonPacket**](../netadapter/nf-netadapter-netadapterreportwakereasonpacket.md)

