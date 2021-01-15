---
UID: NS:wdm._DOMAIN_CONFIGURATION_ARM64
title: _DOMAIN_CONFIGURATION_ARM64 (wdm.h)
description: Contains information required to configure a domain for an ARM64 system.
ms.date: 10/19/2018
tech.root: kernel
keywords: ["DOMAIN_CONFIGURATION_ARM64 structure"]
ms.keywords: _DOMAIN_CONFIGURATION_ARM64, *PDOMAIN_CONFIGURATION_ARM64, DOMAIN_CONFIGURATION_ARM64,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DOMAIN_CONFIGURATION_ARM64, *PDOMAIN_CONFIGURATION_ARM64
targetos: Windows
f1_keywords:
 - _DOMAIN_CONFIGURATION_ARM64
 - wdm/_DOMAIN_CONFIGURATION_ARM64
 - PDOMAIN_CONFIGURATION_ARM64
 - wdm/PDOMAIN_CONFIGURATION_ARM64
 - DOMAIN_CONFIGURATION_ARM64
 - wdm/DOMAIN_CONFIGURATION_ARM64
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DOMAIN_CONFIGURATION_ARM64
 - PDOMAIN_CONFIGURATION_ARM64
 - DOMAIN_CONFIGURATION_ARM64
---

# _DOMAIN_CONFIGURATION_ARM64 structure


## -description

Contains information required to configure a domain for an ARM64 system.

## -struct-fields

### -field Ttbr0

The base address of translation table 0.

### -field Ttbr1

The base address of translation table 0.

### -field Mair0

Memory attribute indirection registers 0.

### -field Mair1

Memory attribute indirection registers 1.

### -field InputSize0

Desired input address width for TTBR0.

### -field InputSize1

Desired input address width for TTBR1.

### -field CoherentTableWalks

Enables or disables coherent translation table walks. This is available starting in Windows 10, version 1809.

### -field TranslationEnabled

Enables or disables translations. If not enabled, all transactions bypass S1 translations. This is available starting in Windows 10, version 1809.

## -remarks

## -see-also

