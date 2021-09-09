---
UID: NS:dot11wificxtypes._WDI_DATA_RATE_ENTRY
tech.root: netvista
title: WDI_DATA_RATE_ENTRY (dot11wificxtypes.h)
ms.date: 06/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_DATA_RATE_ENTRY struct defines a data rate entry.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WDI_DATA_RATE_ENTRY, *PWDI_DATA_RATE_ENTRY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_DATA_RATE_ENTRY
 - PWDI_DATA_RATE_ENTRY
 - WDI_DATA_RATE_ENTRY
f1_keywords:
 - _WDI_DATA_RATE_ENTRY
 - dot11wificxtypes/_WDI_DATA_RATE_ENTRY
 - PWDI_DATA_RATE_ENTRY
 - dot11wificxtypes/PWDI_DATA_RATE_ENTRY
 - WDI_DATA_RATE_ENTRY
 - dot11wificxtypes/WDI_DATA_RATE_ENTRY
dev_langs:
 - c++
---

## -description

The **WDI_DATA_RATE_ENTRY** structure defines a data rate entry.

## -struct-fields

### -field DataRateFlag

Specifies data rate flags as defined in [**WDI_DATA_RATE_FLAGS**](ne-dot11wificxtypes-wdi_data_rate_flags.md).

### -field DataRateValue

Specifies the data rate in units of 500 kilobits per second. The value is in the range from 0x0002 through 0xffff.


## -remarks

## -see-also

[**WDI_DATA_RATE_FLAGS**](ne-dot11wificxtypes-wdi_data_rate_flags.md)