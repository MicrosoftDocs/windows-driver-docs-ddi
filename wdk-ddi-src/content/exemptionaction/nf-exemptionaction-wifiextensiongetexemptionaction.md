---
UID: NF:exemptionaction.WifiExtensionGetExemptionAction
tech.root: netvista
title: WifiExtensionGetExemptionAction
ms.date: 03/25/2024
targetos: Windows
description: The WifiExtensionGetExemptionAction function retrieves the exemption action information for a packet.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: exemptionaction.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 21H2
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
 - exemptionaction.h
api_name:
 - WifiExtensionGetExemptionAction
f1_keywords:
 - WifiExtensionGetExemptionAction
 - exemptionaction/WifiExtensionGetExemptionAction
dev_langs:
 - c++
helpviewer_keywords:
 - WifiExtensionGetExemptionAction
---

## -description

The **WifiExtensionGetExemptionAction** function retrieves the exemption action information for a packet.

## -parameters

### -param Extension

A pointer to a [**NET_EXTENSION**](../extension/ns-extension-_net_extension.md) structure that describes the exemption action information for this packet.

### -param Index

The index in the packet ring for the target [**NET_PACKET**](../packet/ns-packet-_net_packet.md).

## -returns

Returns a pointer to a [**NET_PACKET_WIFI_EXEMPTION_ACTION**](../exemptionactiontypes/ns-exemptionactiontypes-net_packet_wifi_exemption_action.md) structure that holds the exemption action information for this packet.

## -remarks



## -see-also

[**NET_PACKET_WIFI_EXEMPTION_ACTION**](../exemptionactiontypes/ns-exemptionactiontypes-net_packet_wifi_exemption_action.md)