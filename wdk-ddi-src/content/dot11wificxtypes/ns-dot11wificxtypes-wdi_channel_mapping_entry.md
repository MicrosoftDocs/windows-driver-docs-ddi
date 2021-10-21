---
UID: NS:dot11wificxtypes._WDI_CHANNEL_MAPPING_ENTRY
tech.root: netvista
title: WDI_CHANNEL_MAPPING_ENTRY (dot11wificxtypes.h)
ms.date: 07/27/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_CHANNEL_MAPPING_ENTRY struct defines a channel mapping entry.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WDI_CHANNEL_MAPPING_ENTRY, *PWDI_CHANNEL_MAPPING_ENTRY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_CHANNEL_MAPPING_ENTRY
 - PWDI_CHANNEL_MAPPING_ENTRY
 - WDI_CHANNEL_MAPPING_ENTRY
f1_keywords:
 - _WDI_CHANNEL_MAPPING_ENTRY
 - dot11wificxtypes/_WDI_CHANNEL_MAPPING_ENTRY
 - PWDI_CHANNEL_MAPPING_ENTRY
 - dot11wificxtypes/PWDI_CHANNEL_MAPPING_ENTRY
 - WDI_CHANNEL_MAPPING_ENTRY
 - dot11wificxtypes/WDI_CHANNEL_MAPPING_ENTRY
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) is in maintenance mode and will only receive high priority fixes.

The **WDI_CHANNEL_MAPPING_ENTRY** structure defines a channel mapping entry.

## -struct-fields

### -field ChannelNumber

Specifies the logical channel number.

### -field ChannelCenterFrequency

Specifies the center frequency for the channel in MHz.

## -remarks

The **WDI_CHANNEL_MAPPING_ENTRY** struct is a value in the [**WDI_TLV_CHANNEL_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-channel-list) TLV.

## -see-also

[**WDI_TLV_CHANNEL_LIST**](/windows-hardware/drivers/netcx/wdi-tlv-channel-list)
