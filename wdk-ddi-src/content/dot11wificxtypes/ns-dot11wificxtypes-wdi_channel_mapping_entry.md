---
UID: NS:dot11wificxtypes._WDI_CHANNEL_MAPPING_ENTRY
tech.root: netvista
<<<<<<< HEAD
title: WDI_CHANNEL_MAPPING_ENTRY (dot11wificxtypes.h)
ms.date: 07/27/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_CHANNEL_MAPPING_ENTRY struct defines a channel mapping entry.
=======
title: WDI_CHANNEL_MAPPING_ENTRY
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_CHANNEL_MAPPING_ENTRY structure for internal use only. Don't use this structure in your code."
>>>>>>> main
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
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