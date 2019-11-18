---
UID: NS:netadapter._NET_ADAPTER_WAKE_REASON_PACKET
title: NET_ADAPTER_WAKE_REASON_PACKET (netadapter.h)
author: windows-driver-content
description: The NET_ADAPTER_WAKE_REASON_PACKET structure describes a network packet (known as a wake packet) that caused the network adapter to generate a wake-up event.
tech.root: netvista
ms.assetid: b6693c4b-f299-4437-953c-868e6238c9b2
ms.author: windowsdriverdev
ms.date: 10/25/2019
ms.topic: struct
f1_keywords:
 - "netadapter/NET_ADAPTER_WAKE_REASON_PACKET"
ms.keywords: NET_ADAPTER_WAKE_REASON_PACKET, NET_ADAPTER_WAKE_REASON_PACKET, 
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: NET_ADAPTER_WAKE_REASON_PACKET
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
targetos: Windows
ms.custom: Vb
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

Call [**NET_ADAPTER_WAKE_REASON_PACKET_INIT**](../netadapter/nf-netadapter-net_adapter_wake_reason_packet_init.md) to initialize this structure.

A **NET_ADAPTER_WAKE_REASON_PACKET** structure is passed as an input parameter to [**NetAdapterReportWakeReasonPacket**](../netadapter/nf-netadapter-netadapterreportwakereasonpacket.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_REASON_PACKET_INIT**](../netadapter/nf-netadapter-net_adapter_wake_reason_packet_init.md)

[**NetAdapterReportWakeReasonPacket**](../netadapter/nf-netadapter-netadapterreportwakereasonpacket.md)