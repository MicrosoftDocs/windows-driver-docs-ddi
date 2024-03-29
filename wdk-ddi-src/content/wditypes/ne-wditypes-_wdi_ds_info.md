---
UID: NE:wditypes._WDI_DS_INFO
title: _WDI_DS_INFO (wditypes.h)
description: The WDI_DS_INFO enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to.
old-location: netvista\wdi_ds_info.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_DS_INFO enumeration"]
ms.keywords: WDI_DS_CHANGED, WDI_DS_INFO, WDI_DS_INFO enumeration [Device and Driver Installation], WDI_DS_UNCHANGED, WDI_DS_UNKNOWN, _WDI_DS_INFO, netvista.wdi_ds_info, netvista.wifi_ds_info, wditypes/WDI_DS_CHANGED, wditypes/WDI_DS_INFO, wditypes/WDI_DS_UNCHANGED, wditypes/WDI_DS_UNKNOWN
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
req.typenames: WDI_DS_INFO
f1_keywords:
 - _WDI_DS_INFO
 - wditypes/_WDI_DS_INFO
 - WDI_DS_INFO
 - wditypes/WDI_DS_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_DS_INFO
 - WDI_DS_INFO
---

# _WDI_DS_INFO enumeration


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The WDI_DS_INFO enumeration defines values that specify whether the port is connected to the same DS that it was previously associated to.

## -enum-fields

### -field WDI_DS_CHANGED

New DS.

### -field WDI_DS_UNCHANGED

Same DS as previously associated.

### -field WDI_DS_UNKNOWN

Unable to determine if the DS has changed.

### -field WDI_DS_MAX

