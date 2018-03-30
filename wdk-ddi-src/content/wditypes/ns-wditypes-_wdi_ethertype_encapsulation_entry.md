---
UID: NS:wditypes._WDI_ETHERTYPE_ENCAPSULATION_ENTRY
title: "_WDI_ETHERTYPE_ENCAPSULATION_ENTRY"
author: windows-driver-content
description: The WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure defines an EtherType encapsulation entry.
old-location: netvista\wdi_ethertype_encapsulation_entry.htm
old-project: netvista
ms.assetid: 49FE4EC0-B735-48C0-B26E-E165CA840D12
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWDI_ETHERTYPE_ENCAPSULATION_ENTRY, PWDI_ETHERTYPE_ENCAPSULATION_ENTRY, PWDI_ETHERTYPE_ENCAPSULATION_ENTRY structure pointer [Device and Driver Installation], WDI_ETHERTYPE_ENCAPSULATION_ENTRY, WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure [Device and Driver Installation], _WDI_ETHERTYPE_ENCAPSULATION_ENTRY, netvista.wdi_ethertype_encapsulation_entry, netvista.wifi_ethertype_encapsulation_entry, wditypes/PWDI_ETHERTYPE_ENCAPSULATION_ENTRY, wditypes/WDI_ETHERTYPE_ENCAPSULATION_ENTRY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wditypes.hpp
api_name:
-	WDI_ETHERTYPE_ENCAPSULATION_ENTRY
product: Windows
targetos: Windows
req.typenames: WDI_ETHERTYPE_ENCAPSULATION_ENTRY, *PWDI_ETHERTYPE_ENCAPSULATION_ENTRY
req.product: Windows 10 or later.
---

# _WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure


## -description


The 
  WDI_ETHERTYPE_ENCAPSULATION_ENTRY structure defines an EtherType encapsulation entry.


## -struct-fields




### -field EtherType

The value of the IEEE EtherType in big-endian byte order.


### -field EncapsulationType

The type of encapsulation to be performed on the specified EtherType.

