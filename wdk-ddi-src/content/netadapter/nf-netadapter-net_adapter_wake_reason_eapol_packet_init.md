---
UID: NF:netadapter.NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT
tech.root: netvista
title: NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT initializes a NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES struct when reporting that a EAPOL packet caused a wake-up event.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.idl: 
req.include-header: netadaptercx.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - netadapter.h
api_name:
 - NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT
f1_keywords:
 - NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT
 - netadapter/NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT
dev_langs:
 - c++
---

## -description

The client driver calls the  **NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT** function to initialize a [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md) structure when reporting that an EAP over LAN (EAPOL) packet caused a wake-up event.

## -parameters

### -param Reason

[out] A pointer to a driver allocated [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md) structure.

## -remarks

When the [**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md) is
NetWakeSourceTypeEapolPacket, call **NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT** to initialize the [**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md) structure. Call [**NetAdapterReportWakeReasonPacket**](./nf-netadapter-netadapterreportwakereasonpacket.md) to report this wake reason to NetAdapterCx.

This function zeroes out the memory for the **NET_ADAPTER_WAKE_REASON_PACKET** structure, sets the **Size** member, and sets the **PatternId** member to NetAdapterWakeEapolPatternId.

## -see-also

[**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md)

[Configuring NetAdapterCx Power Management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_REASON_PACKET**](../netadapter/ns-netadapter-_net_adapter_wake_reason_packet.md)

[**NetAdapterReportWakeReasonPacket**](./nf-netadapter-netadapterreportwakereasonpacket.md)

[**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md)
