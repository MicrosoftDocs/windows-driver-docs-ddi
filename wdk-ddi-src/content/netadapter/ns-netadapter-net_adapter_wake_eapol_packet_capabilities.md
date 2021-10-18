---
UID: NS:netadapter._NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
tech.root: netvista
title: NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
ms.date: 04/15/2021
targetos: Windows
description: NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES describes a network adapter's WoL capabilities for waking from an EAPOL packet.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: netadapter.h
req.include-header: netadaptercx.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - _NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
 - NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
f1_keywords:
 - _NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
 - netadapter/_NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
 - NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
 - netadapter/NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES
dev_langs:
 - c++
---

## -description

The **NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES** structure describes a network adapter's wake on LAN (WoL) capabilities for waking from an EAP over LAN (EAPOL) request identifier message.

## -struct-fields

### -field Size

The size of this structure in bytes.

### -field EapolPacket

A boolean value that describes if the network adapter is capable of waking from an EAPOL packet.

## -remarks

Call [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT**](nf-netadapter-net_adapter_wake_eapol_packet_capabilities_init.md) to initialize this structure, then call [**NetAdapterWakeSetEapolPacketCapabilities**](nf-netadapter-netadapterwakeseteapolpacketcapabilities.md) to set the network adapter's EAPOL packet WoL capabilities. Client drivers typically call **NetAdapterWakeSetEapolPacketCapabilities** when starting a network adapter, but before calling [**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md).

When reporting that a [**NET_WAKE_SOURCE_TYPE**](../netwakesource/ne-netwakesource-_net_wake_source_type.md) is
NetWakeSourceTypeEapolPacket, call [**NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT**](nf-netadapter-net_adapter_wake_reason_eapol_packet_init.md) to initialize a **NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES** structure.

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT**](nf-netadapter-net_adapter_wake_eapol_packet_capabilities_init.md)

[**NET_ADAPTER_WAKE_REASON_EAPOL_PACKET_INIT**](nf-netadapter-net_adapter_wake_reason_eapol_packet_init.md)

[**NetAdapterWakeSetEapolPacketCapabilities**](nf-netadapter-netadapterwakeseteapolpacketcapabilities.md)

[**NetAdapterStart**](../netadapter/nf-netadapter-netadapterstart.md)

