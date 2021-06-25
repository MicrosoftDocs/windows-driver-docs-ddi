---
UID: NE:dot11wificxtypes._WDI_P2P_DISCOVER_TYPE
tech.root: netvista
title: WDI_P2P_DISCOVER_TYPE (dot11wificxtypes.h)
ms.date: 06/24/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_DISCOVER_TYPE enum defines the Wi-Fi Direct discovery types.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11 Windows 11
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
 - _WDI_P2P_DISCOVER_TYPE
 - WDI_P2P_DISCOVER_TYPE
f1_keywords:
 - _WDI_P2P_DISCOVER_TYPE
 - dot11wificxtypes/_WDI_P2P_DISCOVER_TYPE
 - WDI_P2P_DISCOVER_TYPE
 - dot11wificxtypes/WDI_P2P_DISCOVER_TYPE
dev_langs:
 - c++
---

## -description

The WDI_P2P_DISCOVER_TYPE enumeration defines the Wi-Fi Direct discovery types.

## -enum-fields

### -field WDI_P2P_DISCOVER_TYPE_SCAN_ONLY

Device discovery occurs only during the scan phase. Adapter should scan each channel at least once every 250 milliseconds.

### -field WDI_P2P_DISCOVER_TYPE_FIND_ONLY

Device discovery occurs only during the find phase.

### -field WDI_P2P_DISCOVER_TYPE_AUTO

Device discovery is determined by the port.

### -field WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS

Port must perform device discovery by scanning only Wi-Fi Direct social channels. In this setting, the adapter should scan each social channel at least once every 250 milliseconds.

### -field WDI_P2P_DISCOVER_TYPE_MAX_VALUE

## -remarks

The WDI_P2P_DISCOVER_TYPE enum is a parameter of the [**WDI_TLV_P2P_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-discover-mode) TLV. 

## -see-also

[**WDI_TLV_P2P_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-discover-mode)