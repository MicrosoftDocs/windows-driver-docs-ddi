---
UID: NS:wdm._DOMAIN_CONFIGURATION
title: _DOMAIN_CONFIGURATION (wdm.h)
description: Contains information required to configure a domain.
ms.assetid: 18372649-3eaa-4a4f-b2a1-30978179d14c
ms.date: 10/19/2018
tech.root: kernel
keywords: ["DOMAIN_CONFIGURATION structure"]
ms.keywords: _DOMAIN_CONFIGURATION, DOMAIN_CONFIGURATION, *PDOMAIN_CONFIGURATION,
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DOMAIN_CONFIGURATION, *PDOMAIN_CONFIGURATION
targetos: Windows
f1_keywords:
 - _DOMAIN_CONFIGURATION
 - wdm/_DOMAIN_CONFIGURATION
 - PDOMAIN_CONFIGURATION
 - wdm/PDOMAIN_CONFIGURATION
 - DOMAIN_CONFIGURATION
 - wdm/DOMAIN_CONFIGURATION
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DOMAIN_CONFIGURATION
---

# _DOMAIN_CONFIGURATION structure


## -description

Contains information required to configure a domain. This structure is used by the [_IOMMU_DOMAIN_CONFIGURE_](nc-wdm-iommu_domain_configure.md) callback function.

## -struct-fields

### -field Type

A [**DOMAIN_CONFIGURATION_ARCH**](ne-wdm-_domain_configuration_arch.md)-type value that indicates the domain architecture.

### -field Arm64

A [**DOMAIN_CONFIGURATION_ARM64**](ns-wdm-_domain_configuration_arm64.md) structure that contains the domain configuration information for an ARM64 system.

## -remarks

## -see-also

