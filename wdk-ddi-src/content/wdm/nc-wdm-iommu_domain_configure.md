---
UID: NC:wdm.IOMMU_DOMAIN_CONFIGURE
title: IOMMU_DOMAIN_CONFIGURE (wdm.h)
description: Configures a domain for use.
tech.root: kernel
ms.date: 01/19/2023
keywords: ["IOMMU_DOMAIN_CONFIGURE callback function"]
req.header: wdm.h
req.include-header: Wdm.h
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
targetos: Windows
f1_keywords:
 - IOMMU_DOMAIN_CONFIGURE
 - wdm/IOMMU_DOMAIN_CONFIGURE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - IOMMU_DOMAIN_CONFIGURE
---

## -description

Configures a domain for use. All DMA blocked until the domain is configured.

## -parameters

### -param Domain [_In_]

A pointer to the handle to the domain.

### -param Configuration [_In_]

A pointer to a [**DOMAIN_CONFIGURATION**](ns-wdm-_domain_configuration.md) structure that contains the new configuration for the domain.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

If the domain being configured is OS managed (via [**IOMMU_DOMAIN_CREATE**](./nc-wdm-iommu_domain_create.md)) or is not of type DomainTypeUnmanaged (via [IOMMU_DOMAIN_CREATE_EX](./nc-wdm-iommu_domain_create_ex.md)) then it cannot be configured and the function will return STATUS_INVALID_PARAMETER_1

## -see-also

[**IOMMU_DOMAIN_CREATE**](./nc-wdm-iommu_domain_create.md)

[**IOMMU_DOMAIN_CREATE_EX**](./nc-wdm-iommu_domain_create_ex.md)

[**DOMAIN_CONFIGURATION**](ns-wdm-_domain_configuration.md)
