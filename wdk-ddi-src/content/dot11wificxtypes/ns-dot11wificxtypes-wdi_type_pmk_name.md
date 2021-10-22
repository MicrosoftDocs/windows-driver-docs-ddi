---
UID: NS:dot11wificxtypes._WDI_TYPE_PMK_NAME
tech.root: netvista
title: WDI_TYPE_PMK_NAME (dot11wificxtypes.h)
ms.date: 06/18/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_TYPE_PMK_NAME struct defines the PMKR0Name or PMKR1Name (802.11r).
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
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_TYPE_PMK_NAME
 - PWDI_TYPE_PMK_NAME
 - WDI_TYPE_PMK_NAME
f1_keywords:
 - _WDI_TYPE_PMK_NAME
 - dot11wificxtypes/_WDI_TYPE_PMK_NAME
 - PWDI_TYPE_PMK_NAME
 - dot11wificxtypes/PWDI_TYPE_PMK_NAME
 - WDI_TYPE_PMK_NAME
 - dot11wificxtypes/WDI_TYPE_PMK_NAME
dev_langs:
 - c++
---

## -description

> [!IMPORTANT]
> This topic is part of the [WiFiCx driver model](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx). WiFiCx is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features. The previous Wi-Fi driver model [WDI](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) is in maintenance mode and will only receive high priority fixes.

The **WDI_TYPE_PMK_NAME** structure defines the PMKR0Name or PMKR1Name (802.11r).

## -struct-fields

### -field Name

The PMKR0Name or PMKR1Name.

## -remarks

The **WDI_TYPE_PMK_NAME** structure is a paramter of the [WDI_TLV_FT_PMKR0NAME](/windows-hardware/drivers/netcx/wdi-tlv-ft-pmkr0name) TLV.  

## -see-also

[WDI_TLV_FT_PMKR0NAME](/windows-hardware/drivers/netcx/wdi-tlv-ft-pmkr0name)
