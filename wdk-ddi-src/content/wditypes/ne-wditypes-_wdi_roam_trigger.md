---
UID: NE:wditypes._WDI_ROAM_TRIGGER
title: _WDI_ROAM_TRIGGER (wditypes.h)
description: The WDI_ROAM_TRIGGER enumeration defines roam triggers.
old-location: netvista\wdi_roam_trigger.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_ROAM_TRIGGER enumeration"]
ms.keywords: WDI_ROAM_TRIGGER, WDI_ROAM_TRIGGER enumeration [Network Drivers Starting with Windows Vista], WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST, WDI_ROAM_TRIGGER_OTHER, _WDI_ROAM_TRIGGER, netvista.wdi_roam_trigger, wditypes/WDI_ROAM_TRIGGER, wditypes/WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST, wditypes/WDI_ROAM_TRIGGER_OTHER
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
req.typenames: WDI_ROAM_TRIGGER
f1_keywords:
 - _WDI_ROAM_TRIGGER
 - wditypes/_WDI_ROAM_TRIGGER
 - WDI_ROAM_TRIGGER
 - wditypes/WDI_ROAM_TRIGGER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_ROAM_TRIGGER
 - WDI_ROAM_TRIGGER
---

# _WDI_ROAM_TRIGGER enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide.md) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx.md) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_ROAM_TRIGGER enumeration defines roam triggers.

## -enum-fields

### -field WDI_ROAM_TRIGGER_OTHER

None.

### -field WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST

This value is for roams due to a BSS Transition Request by the AP with the Disassociation Imminent bit set.

