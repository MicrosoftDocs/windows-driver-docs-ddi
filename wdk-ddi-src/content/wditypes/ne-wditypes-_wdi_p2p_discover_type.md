---
UID: NE:wditypes._WDI_P2P_DISCOVER_TYPE
title: _WDI_P2P_DISCOVER_TYPE (wditypes.h)
description: The WDI_P2P_DISCOVER_TYPE enumeration defines the Wi-Fi Direct discovery types.
old-location: netvista\wdi_p2p_discover_type.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_P2P_DISCOVER_TYPE enumeration"]
ms.keywords: WDI_P2P_DISCOVER_TYPE, WDI_P2P_DISCOVER_TYPE enumeration [Device and Driver Installation], WDI_P2P_DISCOVER_TYPE_AUTO, WDI_P2P_DISCOVER_TYPE_FIND_ONLY, WDI_P2P_DISCOVER_TYPE_SCAN_ONLY, WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS, _WDI_P2P_DISCOVER_TYPE, netvista.wdi_p2p_discover_type, netvista.wifi_p2p_discover_type, wditypes/WDI_P2P_DISCOVER_TYPE, wditypes/WDI_P2P_DISCOVER_TYPE_AUTO, wditypes/WDI_P2P_DISCOVER_TYPE_FIND_ONLY, wditypes/WDI_P2P_DISCOVER_TYPE_SCAN_ONLY, wditypes/WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS
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
req.typenames: WDI_P2P_DISCOVER_TYPE
f1_keywords:
 - _WDI_P2P_DISCOVER_TYPE
 - wditypes/_WDI_P2P_DISCOVER_TYPE
 - WDI_P2P_DISCOVER_TYPE
 - wditypes/WDI_P2P_DISCOVER_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_P2P_DISCOVER_TYPE
 - WDI_P2P_DISCOVER_TYPE
---

# _WDI_P2P_DISCOVER_TYPE enumeration


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

