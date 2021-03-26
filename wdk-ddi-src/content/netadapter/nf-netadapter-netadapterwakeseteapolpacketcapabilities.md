---
UID: NF:netadapter.NetAdapterWakeSetEapolPacketCapabilities
tech.root: netvista
title: NetAdapterWakeSetEapolPacketCapabilities
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NetAdapterWakeSetEapolPacketCapabilities sets a net adapter's EAPOL packet WoL capabilities.
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
 - HeaderDef
api_location:
 - netadapter.h
api_name:
 - NetAdapterWakeSetEapolPacketCapabilities
f1_keywords:
 - NetAdapterWakeSetEapolPacketCapabilities
 - netadapter/NetAdapterWakeSetEapolPacketCapabilities
dev_langs:
 - c++
---

## -description

The **NetAdapterWakeSetEapolPacketCapabilities** function sets a net adapter's EAP over LAN (EAPOL) packet wake on LAN (WoL) capabilities.

## -parameters

### -param Adapter

[_In_] A handle to a NETADAPTER object the client driver previously created with a call to [**NetAdapterCreate**](nf-netadapter-netadaptercreate.md).

### -param Capabilities

[_In_] A pointer to a driver-allocated and initialized [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md) structure that describes the net adapter's EAPOL packet WoL capabilities.

## -remarks

Client drivers must call [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT**](nf-netadapter-net_adapter_wake_eapol_packet_capabilities_init.md) to initialize the **NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES** structure, then set the structure's members appropriately before calling this function. Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md)

[**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT**](nf-netadapter-net_adapter_wake_eapol_packet_capabilities_init.md)

[*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)