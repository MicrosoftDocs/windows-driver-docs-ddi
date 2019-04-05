---
UID: NS:wditypes._WDI_DATA_RATE_ENTRY
title: _WDI_DATA_RATE_ENTRY (wditypes.h)
description: The WDI_DATA_RATE_ENTRY structure defines a data rate entry.
old-location: netvista\wdi_data_rate_entry.htm
tech.root: netvista
ms.assetid: 16A4B49B-9912-40BE-80E8-68416B966B71
ms.date: 05/02/2018
ms.keywords: "*PWDI_DATA_RATE_ENTRY, PWDI_DATA_RATE_ENTRY, PWDI_DATA_RATE_ENTRY structure pointer [Device and Driver Installation], WDI_DATA_RATE_ENTRY, WDI_DATA_RATE_ENTRY structure [Device and Driver Installation], _WDI_DATA_RATE_ENTRY, netvista.wdi_data_rate_entry, netvista.wifi_data_rate_entry, wditypes/PWDI_DATA_RATE_ENTRY, wditypes/WDI_DATA_RATE_ENTRY"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wditypes.hpp
api_name:
- WDI_DATA_RATE_ENTRY
product:
- Windows
targetos: Windows
req.typenames: WDI_DATA_RATE_ENTRY, *PWDI_DATA_RATE_ENTRY
---

# _WDI_DATA_RATE_ENTRY structure


## -description


The 
  WDI_DATA_RATE_ENTRY structure defines a data rate entry.


## -struct-fields




### -field DataRateFlag

Specifies data rate flags as defined in WDI_DATA_RATE_FLAGS.


### -field DataRateValue

Specifies the data rate in units of 500 kilobits per second. The value is in the range from 0x0002 through 0xffff.


