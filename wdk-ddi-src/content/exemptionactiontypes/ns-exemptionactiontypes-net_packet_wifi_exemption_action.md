---
UID: NS:exemptionactiontypes._NET_PACKET_WIFI_EXEMPTION_ACTION
tech.root: netvista
title: NET_PACKET_WIFI_EXEMPTION_ACTION
ms.date: 03/25/2024
targetos: Windows
description: The NET_PACKET_WIFI_EXEMPTION_ACTION structure contains the exemption action information for a packet.
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

The **NET_PACKET_WIFI_EXEMPTION_ACTION** structure contains the exemption action information for a packet.

## -struct-fields

### -field ExemptionAction

A bit field that specifies a flag from [**WDI_EXEMPTION_ACTION_TYPE**](../dot11wificxintf/ne-dot11wificxintf-wdi_exemption_action_type.md).

## -remarks

Client drivers can obtain this structure for a packet by calling [**WifiExtensionGetExemptionAction**](../exemptionaction/nf-exemptionaction-wifiextensiongetexemptionaction.md).

## -see-also

[**WifiExtensionGetExemptionAction**](../exemptionaction/nf-exemptionaction-wifiextensiongetexemptionaction.md)

[**WDI_EXEMPTION_ACTION_TYPE**](../dot11wificxintf/ne-dot11wificxintf-wdi_exemption_action_type.md)