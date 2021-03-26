---
UID: NF:netadapter.NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT
tech.root: netvista
title: NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT
ms.date: 04/15/2021
ms.topic: language-reference
targetos: Windows
description: NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT initializes a NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES structure. 
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
 - NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT
f1_keywords:
 - NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT
 - netadapter/NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT
dev_langs:
 - c++
---

## -description

The **NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT** function initializes a [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md) structure. 

## -parameters

### -param Capabilities

[_Out_] A pointer to a driver-allocated [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md) structure.

## -remarks

The client driver calls **NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES_INIT** to initialize a [**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md) structure. The driver passes the initialized **NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES** structure as a parameter to the [**NetAdapterWakeSetEapolPacketCapabilities**](nf-netadapter-netadapterwakeseteapolpacketcapabilities.md) function to register it.

## -see-also

[**NetAdapterWakeSetEapolPacketCapabilities**](nf-netadapter-netadapterwakeseteapolpacketcapabilities.md)

[**NET_ADAPTER_WAKE_EAPOL_PACKET_CAPABILITIES**](ns-netadapter-net_adapter_wake_eapol_packet_capabilities.md)