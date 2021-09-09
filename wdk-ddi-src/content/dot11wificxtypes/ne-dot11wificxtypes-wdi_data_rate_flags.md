---
UID: NE:dot11wificxtypes._WDI_DATA_RATE_FLAGS
tech.root: netvista
<<<<<<< HEAD
title: WDI_DATA_RATE_FLAGS (dot11wificxtypes.h)
ms.date: 06/22/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_DATA_RATE_FLAGS enum defines the data rate flags.
=======
title: WDI_DATA_RATE_FLAGS
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_DATA_RATE_FLAGS enumeration for internal use only. Don't use this enumeration in your code."
>>>>>>> main
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
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
 - _WDI_DATA_RATE_FLAGS
 - WDI_DATA_RATE_FLAGS
f1_keywords:
 - _WDI_DATA_RATE_FLAGS
 - dot11wificxtypes/_WDI_DATA_RATE_FLAGS
 - WDI_DATA_RATE_FLAGS
 - dot11wificxtypes/WDI_DATA_RATE_FLAGS
dev_langs:
 - c++
---

## -description

The **WDI_DATA_RATE_FLAGS** enumeration defines the data rate flags.

## -enum-fields

### -field WDI_DATA_RATE_NON_STANDARD

The data rate is not a standard data rate defined in the IEEE 802.11 standards.

### -field WDI_DATA_RATE_RX_RATE

The data rate can be used for RX.

### -field WDI_DATA_RATE_TX_RATE

The data rate can be used for TX.

## -remarks

The **WDI_DATA_RATE_FLAGS** enum is a member of the [**WDI_DATA_RATE_ENTRY**](ns-dot11wificxtypes-wdi_data_rate_entry.md) structure.


## -see-also

[**WDI_DATA_RATE_ENTRY**](ns-dot11wificxtypes-wdi_data_rate_entry.md)