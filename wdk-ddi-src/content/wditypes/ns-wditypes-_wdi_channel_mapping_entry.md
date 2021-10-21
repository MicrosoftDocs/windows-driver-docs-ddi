---
UID: NS:wditypes._WDI_CHANNEL_MAPPING_ENTRY
title: _WDI_CHANNEL_MAPPING_ENTRY (wditypes.h)
description: The WDI_CHANNEL_MAPPING_ENTRY structure defines a channel mapping entry.
old-location: netvista\wdi_channel_mapping_entry.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_CHANNEL_MAPPING_ENTRY structure"]
ms.keywords: "*PWDI_CHANNEL_MAPPING_ENTRY, PWDI_CHANNEL_MAPPING_ENTRY, PWDI_CHANNEL_MAPPING_ENTRY structure pointer [Device and Driver Installation], WDI_CHANNEL_MAPPING_ENTRY, WDI_CHANNEL_MAPPING_ENTRY structure [Device and Driver Installation], _WDI_CHANNEL_MAPPING_ENTRY, netvista.wdi_channel_mapping_entry, netvista.wifi_channel_mapping_entry, wditypes/PWDI_CHANNEL_MAPPING_ENTRY, wditypes/WDI_CHANNEL_MAPPING_ENTRY"
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WDI_CHANNEL_MAPPING_ENTRY, *PWDI_CHANNEL_MAPPING_ENTRY
f1_keywords:
 - _WDI_CHANNEL_MAPPING_ENTRY
 - wditypes/_WDI_CHANNEL_MAPPING_ENTRY
 - PWDI_CHANNEL_MAPPING_ENTRY
 - wditypes/PWDI_CHANNEL_MAPPING_ENTRY
 - WDI_CHANNEL_MAPPING_ENTRY
 - wditypes/WDI_CHANNEL_MAPPING_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_CHANNEL_MAPPING_ENTRY
 - PWDI_CHANNEL_MAPPING_ENTRY
 - WDI_CHANNEL_MAPPING_ENTRY
---

# _WDI_CHANNEL_MAPPING_ENTRY structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  WDI_CHANNEL_MAPPING_ENTRY structure defines a channel mapping entry.

## -struct-fields

### -field ChannelNumber

Specifies the logical channel number.

### -field ChannelCenterFrequency

Specifies the center frequency for the channel in MHz.

