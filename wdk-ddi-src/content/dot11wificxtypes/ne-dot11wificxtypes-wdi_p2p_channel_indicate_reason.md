---
UID: NE:dot11wificxtypes._WDI_P2P_CHANNEL_INDICATE_REASON
tech.root: netvista
title: WDI_P2P_CHANNEL_INDICATE_REASON (dot11wificxtypes.h)
ms.date: 08/04/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_CHANNEL_INDICATE_REASON enum defines Wi-Fi Direct channel indication reason values.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_P2P_CHANNEL_INDICATE_REASON
 - WDI_P2P_CHANNEL_INDICATE_REASON
f1_keywords:
 - _WDI_P2P_CHANNEL_INDICATE_REASON
 - dot11wificxtypes/_WDI_P2P_CHANNEL_INDICATE_REASON
 - WDI_P2P_CHANNEL_INDICATE_REASON
 - dot11wificxtypes/WDI_P2P_CHANNEL_INDICATE_REASON
dev_langs:
 - c++
---

## -description

The **WDI_P2P_CHANNEL_INDICATE_REASON** enumeration defines Wi-Fi Direct channel indication reason values.

## -enum-fields

### -field WDI_P2P_CHANNEL_INDICATE_REASON_UNKNOWN

### -field WDI_P2P_CHANNEL_INDICATE_REASON_NEW_CONNECTION:0x0001

New connection set up.

### -field WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_REQUESTED:0x0002

eCSA request from the peer.

### -field WDI_P2P_CHANNEL_INDICATE_REASON_ECSA_GO_INITIATED:0x0003

eCSA initiated by GO.

### -field WDI_P2P_CHANNEL_INDICATE_REASON_MAX

## -remarks

The **WDI_P2P_CHANNEL_INDICATE_REASON** enum is a value in the [**WDI_TLV_P2P_CHANNEL_INDICATE_REASON**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-channel-indicate-reason) TLV.

## -see-also

[**WDI_TLV_P2P_CHANNEL_INDICATE_REASON**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-channel-indicate-reason)