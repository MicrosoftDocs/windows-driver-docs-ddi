---
UID: NF:netadapter.NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT
title: NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT
ms.date: 08/20/2020
ms.topic: language-reference
targetos: Windows
description: The NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT method initializes a NET_ADAPTER_WAKE_REASON_PACKET when the wake source is a magic packet.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.idl: 
req.include-header: 
req.irql: Any level as long as target memory is resident
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT
f1_keywords:
 - netadapter/NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT
dev_langs:
 - c++
---

## -description

A client driver calls the **NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT** method to initialize a [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) when reporting that the wake source is magic packet entry.

## -parameters

### -param Reason

[out] A pointer to a driver allocated [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure.

## -returns

This method does not return a value.

## -remarks

When the source of a wake-up event from a net adapter is magic packet entry, the [**NET_WAKE_SOURCE_TYPE**](/windows-hardware/drivers/ddi/netwakesource/ne-netwakesource-_net_wake_source_type) is
NetWakeSourceTypeMagicPacket.

To report this wake reason the client driver calls **NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT** to initialize the [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure and then calls [**NetAdapterReportWakeReasonPacket**](/windows-hardware/drivers/ddi/netadapter/nf-netadapter-netadapterreportwakereasonpacket).

This method zeroes out the memory for the **NET_ADAPTER_WAKE_REASON_PACKET** structure, sets the **Size** member, and sets the **PatternId** member.

## -see-also

[**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md)

[**NetAdapterReportWakeReasonPacket**](/windows-hardware/drivers/ddi/netadapter/nf-netadapter-netadapterreportwakereasonpacket)

[**NET_WAKE_SOURCE_TYPE**](/windows-hardware/drivers/ddi/netwakesource/ne-netwakesource-_net_wake_source_type)
