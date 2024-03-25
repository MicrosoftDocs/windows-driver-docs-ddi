---
UID: NS:exemptionactiontypes._NET_PACKET_WIFI_EXEMPTION_ACTION
tech.root: netvista
title: NET_PACKET_WIFI_EXEMPTION_ACTION
ms.date: 03/25/2024
targetos: Windows
description: The NET_PACKET_WIFI_EXEMPTION_ACTION structure specifies the type of encryption exemption for the packet.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: exemptionactiontypes.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 21H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: NET_PACKET_WIFI_EXEMPTION_ACTION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - exemptionactiontypes.h
api_name:
 - _NET_PACKET_WIFI_EXEMPTION_ACTION
 - NET_PACKET_WIFI_EXEMPTION_ACTION
f1_keywords:
 - _NET_PACKET_WIFI_EXEMPTION_ACTION
 - exemptionactiontypes/_NET_PACKET_WIFI_EXEMPTION_ACTION
 - NET_PACKET_WIFI_EXEMPTION_ACTION
 - exemptionactiontypes/NET_PACKET_WIFI_EXEMPTION_ACTION
dev_langs:
 - c++
helpviewer_keywords:
 - _NET_PACKET_WIFI_EXEMPTION_ACTION
---

## -description

The **NET_PACKET_WIFI_EXEMPTION_ACTION** structure specifies the type of encryption exemption for the packet.

## -struct-fields

### -field ExemptionAction

The type of exemption action for the packet. The following exemption types are defined:

`DOT11_EXEMPT_NO_EXEMPTION`

The packet is not exempt from any cipher operations performed by the 802.11 station.

`DOT11_EXEMPT_ALWAYS`

The packet is exempt from any cipher operations performed by the 802.11 station. The 802.11 station must transmit the packet unencrypted.

`DOT11_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE`

The packet is exempt from any cipher operations performed by the 802.11 station only if the station does not have a key-mapping key for the packet's destination media access control (MAC) address. 

## -remarks

Client drivers can obtain this structure for a packet by calling [**WifiExtensionGetExemptionAction**](../exemptionaction/nf-exemptionaction-wifiextensiongetexemptionaction.md).

## -see-also

[**WifiExtensionGetExemptionAction**](../exemptionaction/nf-exemptionaction-wifiextensiongetexemptionaction.md)