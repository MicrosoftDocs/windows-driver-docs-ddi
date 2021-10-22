---
UID: NE:dot11wificxtypes._WDI_ROAM_TRIGGER
tech.root: netvista
title: WDI_ROAM_TRIGGER (dot11wificxtypes.h)
ms.date: 09/15/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_ROAM_TRIGGER enum defines roam triggers.
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
 - _WDI_ROAM_TRIGGER
 - WDI_ROAM_TRIGGER
f1_keywords:
 - _WDI_ROAM_TRIGGER
 - dot11wificxtypes/_WDI_ROAM_TRIGGER
 - WDI_ROAM_TRIGGER
 - dot11wificxtypes/WDI_ROAM_TRIGGER
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_ROAM_TRIGGER** enumeration defines roam triggers.

## -enum-fields

### -field WDI_ROAM_TRIGGER_OTHER:0x00000000

None.

### -field WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST:0x00000001

This value is for roams due to a BSS Transition Request by the AP with the Disassociation Imminent bit set.


## -remarks

## -see-also

