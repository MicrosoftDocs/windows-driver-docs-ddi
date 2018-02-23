---
UID: NE:wditypes._WDI_SCAN_TYPE
title: "_WDI_SCAN_TYPE"
author: windows-driver-content
description: The WDI_SCAN_TYPE enumeration defines the scan types.
old-location: netvista\wdi_scan_type.htm
old-project: netvista
ms.assetid: DF4ECD03-2C2F-44B3-82BE-E57B333AF069
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.wdi_scan_type, WDI_SCAN_TYPE, wditypes/WDI_SCAN_TYPE_PASSIVE_ONLY, WDI_SCAN_TYPE_PASSIVE_ONLY, netvista.wifi_scan_type, WDI_SCAN_TYPE enumeration [Device and Driver Installation], WDI_SCAN_TYPE_ACTIVE_ONLY, WDI_SCAN_TYPE_AUTO, wditypes/WDI_SCAN_TYPE_ACTIVE_ONLY, _WDI_SCAN_TYPE, wditypes/WDI_SCAN_TYPE, wditypes/WDI_SCAN_TYPE_AUTO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wditypes.hpp
apiname:
-	WDI_SCAN_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_SCAN_TYPE
req.product: Windows 10 or later.
---

# _WDI_SCAN_TYPE enumeration


## -description


The WDI_SCAN_TYPE enumeration defines the scan types.


## -syntax


````
typedef enum _WDI_SCAN_TYPE { 
  WDI_SCAN_TYPE_ACTIVE_ONLY   = 1,
  WDI_SCAN_TYPE_PASSIVE_ONLY  = 2,
  WDI_SCAN_TYPE_AUTO          = 3
} WDI_SCAN_TYPE;
````


## -enum-fields




### -field WDI_SCAN_TYPE_ACTIVE_ONLY

The port should transmit a probe request on the channels that it scans. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.


### -field WDI_SCAN_TYPE_PASSIVE_ONLY

The port should not transmit a probe request on the channels that it scans.


### -field WDI_SCAN_TYPE_AUTO

The port can perform an active or passive can or can use a combination of both scan types. It should prefer using Active scans when possible. This is the default scan type setting.


### -field WDI_SCAN_TYPE_MAX_VALUE



