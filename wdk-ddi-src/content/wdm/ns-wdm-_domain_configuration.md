---
UID: NS:wdm._DOMAIN_CONFIGURATION
title: _DOMAIN_CONFIGURATION
author: windows-driver-content
description: Contains information required to configure a domain.
ms.assetid: 18372649-3eaa-4a4f-b2a1-30978179d14c
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	wdm.h
apiname: 
-	_DOMAIN_CONFIGURATION
product:
-	Windows
targetos: Windows
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