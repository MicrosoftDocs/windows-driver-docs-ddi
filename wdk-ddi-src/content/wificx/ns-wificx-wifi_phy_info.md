---
UID: NS:wificx._WIFI_PHY_INFO
tech.root: netvista
<<<<<<< HEAD
title: WIFI_PHY_INFO (wificx.h)
ms.date: 08/27/2021
ms.topic: language-reference
targetos: Windows
description: The WIFI_PHY_INFO structure contains PHY information. 
=======
title: WIFI_PHY_INFO
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WIFI_PHY_INFO structure for internal use only. Don't use this structure in your code."
>>>>>>> main
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WIFI_PHY_INFO
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - _WIFI_PHY_INFO
 - WIFI_PHY_INFO
f1_keywords:
 - _WIFI_PHY_INFO
 - wificx/_WIFI_PHY_INFO
 - WIFI_PHY_INFO
 - wificx/WIFI_PHY_INFO
dev_langs:
 - c++
---

## -description

The **WIFI_PHY_INFO** structure contains PHY information. 

## -struct-fields

### -field PhyType

An [**WDI_PHY_TYPE**](../dot11wificxtypes/ne-dot11wificxtypes-wdi_phy_type.md) enum that specifies the PHY type.

### -field NumberDataRateEntries

The number of data rate entries.

### -field DataRateList

An array of [**WDI_DATA_RATE_ENTRY**](../dot11wificxtypes/ns-dot11wificxtypes-wdi_data_rate_entry.md) structures. 

## -remarks

**WIFI_PHY_INFO** is a member of the [**WIFI_PHY_CAPABILITIES**](ns-wificx-wifi_phy_capabilities.md) structure.

## -see-also

[**WDI_PHY_TYPE**](../dot11wificxtypes/ne-dot11wificxtypes-wdi_phy_type.md)

[**WIFI_PHY_CAPABILITIES**](ns-wificx-wifi_phy_capabilities.md)

[**WDI_DATA_RATE_ENTRY**](../dot11wificxtypes/ns-dot11wificxtypes-wdi_data_rate_entry.md)
