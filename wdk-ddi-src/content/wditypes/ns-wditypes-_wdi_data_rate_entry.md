---
UID: NS:wditypes._WDI_DATA_RATE_ENTRY
title: _WDI_DATA_RATE_ENTRY (wditypes.h)
description: The WDI_DATA_RATE_ENTRY structure defines a data rate entry.
old-location: netvista\wdi_data_rate_entry.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_DATA_RATE_ENTRY structure"]
ms.keywords: "*PWDI_DATA_RATE_ENTRY, PWDI_DATA_RATE_ENTRY, PWDI_DATA_RATE_ENTRY structure pointer [Device and Driver Installation], WDI_DATA_RATE_ENTRY, WDI_DATA_RATE_ENTRY structure [Device and Driver Installation], _WDI_DATA_RATE_ENTRY, netvista.wdi_data_rate_entry, netvista.wifi_data_rate_entry, wditypes/PWDI_DATA_RATE_ENTRY, wditypes/WDI_DATA_RATE_ENTRY"
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
req.typenames: WDI_DATA_RATE_ENTRY, *PWDI_DATA_RATE_ENTRY
f1_keywords:
 - _WDI_DATA_RATE_ENTRY
 - wditypes/_WDI_DATA_RATE_ENTRY
 - PWDI_DATA_RATE_ENTRY
 - wditypes/PWDI_DATA_RATE_ENTRY
 - WDI_DATA_RATE_ENTRY
 - wditypes/WDI_DATA_RATE_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_DATA_RATE_ENTRY
 - PWDI_DATA_RATE_ENTRY
 - WDI_DATA_RATE_ENTRY
---

# _WDI_DATA_RATE_ENTRY structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  WDI_DATA_RATE_ENTRY structure defines a data rate entry.

## -struct-fields

### -field DataRateFlag

Specifies data rate flags as defined in WDI_DATA_RATE_FLAGS.

### -field DataRateValue

Specifies the data rate in units of 500 kilobits per second. The value is in the range from 0x0002 through 0xffff.

