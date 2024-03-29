---
UID: NS:wditypes._WDI_ETHERTYPE_ENCAPSULATION_ENTRY
title: _WDI_ETHERTYPE_ENCAPSULATION_ENTRY (wditypes.h)
description: The WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure defines an EtherType encapsulation entry.
old-location: netvista\wdi_ethertype_encapsulation_entry.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure"]
ms.keywords: "*PWDI_ETHERTYPE_ENCAPSULATION_ENTRY, PWDI_ETHERTYPE_ENCAPSULATION_ENTRY, PWDI_ETHERTYPE_ENCAPSULATION_ENTRY structure pointer [Device and Driver Installation], WDI_ETHERTYPE_ENCAPSULATION_ENTRY, WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure [Device and Driver Installation], _WDI_ETHERTYPE_ENCAPSULATION_ENTRY, netvista.wdi_ethertype_encapsulation_entry, netvista.wifi_ethertype_encapsulation_entry, wditypes/PWDI_ETHERTYPE_ENCAPSULATION_ENTRY, wditypes/WDI_ETHERTYPE_ENCAPSULATION_ENTRY"
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
req.typenames: WDI_ETHERTYPE_ENCAPSULATION_ENTRY, *PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
f1_keywords:
 - _WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - wditypes/_WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - wditypes/PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - wditypes/WDI_ETHERTYPE_ENCAPSULATION_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wditypes.hpp
api_name:
 - _WDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
 - WDI_ETHERTYPE_ENCAPSULATION_ENTRY
---

# _WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The 
  WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure defines an EtherType encapsulation entry.

## -struct-fields

### -field EtherType

The value of the IEEE EtherType in big-endian byte order.

### -field EncapsulationType

The type of encapsulation to be performed on the specified EtherType.

