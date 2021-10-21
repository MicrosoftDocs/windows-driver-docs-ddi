---
UID: NE:dot11wificxtypes._WDI_BSS_SELECTION_FLAGS
tech.root: netvista
title: WDI_BSS_SELECTION_FLAGS (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_BSS_SELECTION_FLAGS enum defines flags for BSS selection.
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
 - _WDI_BSS_SELECTION_FLAGS
 - WDI_BSS_SELECTION_FLAGS
f1_keywords:
 - _WDI_BSS_SELECTION_FLAGS
 - dot11wificxtypes/_WDI_BSS_SELECTION_FLAGS
 - WDI_BSS_SELECTION_FLAGS
 - dot11wificxtypes/WDI_BSS_SELECTION_FLAGS
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) is in maintenance mode and will only receive high priority fixes.

The **WDI_BSS_SELECTION_FLAGS** enumeration defines flags for BSS selection.


## -enum-fields

### -field WDI_BSS_SELECTION_HOST_PREFERRED:0x00000001

Set for BSS entries that the host prefers to connect to. Non-preferred BSS entries would also be provided to the port, but should only be used  for connection if port performs its own BSS ranking.

### -field WDI_BSS_SELECTION_RECENT_ASSOCIATION_ERROR:0x00000002

Set for BSS entries that had recent association failures or were recently disassociated from. This flag is already accounted for by the host when setting WDI_BSS_SELECTION_HOST_PREFERRED.

### -field WDI_BSS_SELECTION_FLAGS_AP_REQUESTED_TRANSITION:0x00000004

Specifies whether this roam was requested by the AP or not (11v BSS Transition management request).

## -remarks

The **WDI_BSS_SELECTION_FLAGS** enum is a value in the [WDI_TLV_BSS_SELECTION_PARAMETERS](/windows-hardware/drivers/network/wdi-tlv-bss-selection-parameters) TLV.

## -see-also

[WDI_TLV_BSS_SELECTION_PARAMETERS](/windows-hardware/drivers/network/wdi-tlv-bss-selection-parameters)
