---
UID: NE:dot11wificxtypes._WDI_P2P_SCAN_TYPE
tech.root: netvista
title: WDI_P2P_SCAN_TYPE (dot11wificxtypes.h)
ms.date: 06/24/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_P2P_SCAN_TYPE enum defines the Wi-Fi Direct scan types.
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
 - _WDI_P2P_SCAN_TYPE
 - WDI_P2P_SCAN_TYPE
f1_keywords:
 - _WDI_P2P_SCAN_TYPE
 - dot11wificxtypes/_WDI_P2P_SCAN_TYPE
 - WDI_P2P_SCAN_TYPE
 - dot11wificxtypes/WDI_P2P_SCAN_TYPE
dev_langs:
 - c++
---

## -description

The WDI_P2P_SCAN_TYPE enumeration defines the Wi-Fi Direct scan types.

## -enum-fields

### -field WDI_P2P_SCAN_TYPE_ACTIVE

Use active scanning during device discovery. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.

### -field WDI_P2P_SCAN_TYPE_PASSIVE

Use passive scanning during device discovery.

### -field WDI_P2P_SCAN_TYPE_AUTO

Adapter determines scan type during device discovery. It should prefer using Active scans when possible. This is the default scan type setting.

### -field WDI_P2P_SCAN_TYPE_MAX_VALUE

## -remarks

The WDI_P2P_SCAN_TYPE enumeration is used in the payload buffer of the [**WDI_TLV_P2P_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-discover-mode) TLV. 

## -see-also

[**WDI_TLV_P2P_DISCOVER_MODE**](/windows-hardware/drivers/netcx/wdi-tlv-p2p-discover-mode)