---
UID: NC:wdm.IOMMU_DOMAIN_CONFIGURE
title: IOMMU_DOMAIN_CONFIGURE
author: windows-driver-content
description: Configures a domain for use.
ms.assetid: 1b5394c2-0dc9-49a2-a749-37c40c60bf3b
ms.date: 
ms.topic: callback
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topictype: 
-	apiref
apitype: 
-	UserDefined
apilocation: 
-	wdm.h
apiname: 
-	IOMMU_DOMAIN_CONFIGURE
product:
-	Windows
targetos: Windows
---

# IOMMU_DOMAIN_CONFIGURE callback function

## -description

Configures a domain for use. All DMA blocked until the domain is configured.

## -prototype

```
//Declaration

IOMMU_DOMAIN_CONFIGURE IommuDomainConfigure; 

// Definition

NTSTATUS IommuDomainConfigure 
(
	PIOMMU_DMA_DOMAIN Domain
	PDOMAIN_CONFIGURATION Configuration
)
{...}

IOMMU_DOMAIN_CONFIGURE *PIOMMU_DOMAIN_CONFIGURE


```

## -parameters

### -param Domain
[_In_] A pointer to the handle to the domain.

### -param Configuration
[_In_] A pointer to a [**DOMAIN_CONFIGURATION**](ns-wdm-_domain_configuration.md) structure that contains the new configuration for the domain.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks


## -see-also
