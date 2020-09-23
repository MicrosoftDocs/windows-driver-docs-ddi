---
UID: NF:netadapter.NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT
title: NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT
ms.date: 08/20/2020
ms.topic: language-reference
targetos: Windows
description: The NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT function initializes a NET_ADAPTER_WAKE_REASON_PACKET when the wake source is a magic packet.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadaptercx.h
req.idl: 
req.include-header: netadaptercx.h 
req.irql: Any level as long as target memory is resident
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 20H2
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

> [!WARNING]
> Some information in this topic relates to pre-released product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 2004.
>
> Currently, NetAdapterCx client drivers cannot be certified.

The client driver calls the  **NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT** function to initialize a [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure when reporting that a magic packet caused a wake-up event.

## -parameters

### -param Reason

[out] A pointer to a driver allocated [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure.

## -returns

This function does not return a value.

## -remarks

When the [**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md) is
NetWakeSourceTypeMagicPacket, call **NET_ADAPTER_WAKE_REASON_MAGIC_PACKET_INIT** to initialize the [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure. Call [**NetAdapterReportWakeReasonPacket**](./nf-netadapter-netadapterreportwakereasonpacket.md) to report this wake reason to NetAdapterCx.

This function zeroes out the memory for the **NET_ADAPTER_WAKE_REASON_PACKET** structure, sets the **Size** member, and sets the **PatternId** member to NetAdapterWakeMagicPatternId.

## -see-also

[Configuring NetAdapterCx Power Management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md)

[**NetAdapterReportWakeReasonPacket**](./nf-netadapter-netadapterreportwakereasonpacket.md)

[**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md)