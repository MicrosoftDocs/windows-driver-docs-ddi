---
UID: NE:wditypes._WDI_P2P_SCAN_TYPE
title: _WDI_P2P_SCAN_TYPE (wditypes.h)
description: The WDI_P2P_SCAN_TYPE enumeration defines the Wi-Fi Direct scan types.
old-location: netvista\wdi_p2p_scan_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_P2P_SCAN_TYPE enumeration"]
ms.keywords: WDI_P2P_SCAN_TYPE, WDI_P2P_SCAN_TYPE enumeration [Device and Driver Installation], WDI_P2P_SCAN_TYPE_ACTIVE, WDI_P2P_SCAN_TYPE_AUTO, WDI_P2P_SCAN_TYPE_PASSIVE, _WDI_P2P_SCAN_TYPE, netvista.wdi_p2p_scan_type, netvista.wifi_p2p_scan_type, wditypes/WDI_P2P_SCAN_TYPE, wditypes/WDI_P2P_SCAN_TYPE_ACTIVE, wditypes/WDI_P2P_SCAN_TYPE_AUTO, wditypes/WDI_P2P_SCAN_TYPE_PASSIVE
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
req.typenames: WDI_P2P_SCAN_TYPE
f1_keywords:
 - _WDI_P2P_SCAN_TYPE
 - wditypes/_WDI_P2P_SCAN_TYPE
 - WDI_P2P_SCAN_TYPE
 - wditypes/WDI_P2P_SCAN_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - WDI_P2P_SCAN_TYPE
---

# _WDI_P2P_SCAN_TYPE enumeration


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

