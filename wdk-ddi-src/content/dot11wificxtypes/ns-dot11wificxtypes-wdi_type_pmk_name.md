---
UID: NS:dot11wificxtypes._WDI_TYPE_PMK_NAME
tech.root: netvista
<<<<<<< HEAD
title: WDI_TYPE_PMK_NAME (dot11wificxtypes.h)
ms.date: 06/18/2021
ms.topic: language-reference
targetos: Windows
description: The WDI_TYPE_PMK_NAME struct defines the PMKR0Name or PMKR1Name (802.11r).
=======
title: WDI_TYPE_PMK_NAME
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WDI_TYPE_PMK_NAME structure for internal use only. Don't use this structure in your code."
>>>>>>> main
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dot11wificxtypes.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11  
=======
req.target-min-winverclnt: Windows 11Windows 11
>>>>>>> main
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dot11wificxtypes.h
api_name:
 - _WDI_TYPE_PMK_NAME
 - PWDI_TYPE_PMK_NAME
 - WDI_TYPE_PMK_NAME
f1_keywords:
 - _WDI_TYPE_PMK_NAME
 - dot11wificxtypes/_WDI_TYPE_PMK_NAME
 - PWDI_TYPE_PMK_NAME
 - dot11wificxtypes/PWDI_TYPE_PMK_NAME
 - WDI_TYPE_PMK_NAME
 - dot11wificxtypes/WDI_TYPE_PMK_NAME
dev_langs:
 - c++
---

## -description

The **WDI_TYPE_PMK_NAME** structure defines the PMKR0Name or PMKR1Name (802.11r).

## -struct-fields

### -field Name

The PMKR0Name or PMKR1Name.

## -remarks

The **WDI_TYPE_PMK_NAME** structure is a paramter of the [WDI_TLV_FT_PMKR0NAME](/windows-hardware/drivers/netcx/wdi-tlv-ft-pmkr0name) TLV.  

## -see-also

[WDI_TLV_FT_PMKR0NAME](/windows-hardware/drivers/netcx/wdi-tlv-ft-pmkr0name)