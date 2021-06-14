---
UID: NS:wdm._IOMMU_DMA_DOMAIN_CREATION_FLAGS
tech.root: kernel
title: IOMMU_DMA_DOMAIN_CREATION_FLAGS
ms.date: 06/10/2021
targetos: Windows
description: 
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: IOMMU_DMA_DOMAIN_CREATION_FLAGS, *PIOMMU_DMA_DOMAIN_CREATION_FLAGS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_DMA_DOMAIN_CREATION_FLAGS
 - PIOMMU_DMA_DOMAIN_CREATION_FLAGS
 - IOMMU_DMA_DOMAIN_CREATION_FLAGS
f1_keywords:
 - _IOMMU_DMA_DOMAIN_CREATION_FLAGS
 - wdm/_IOMMU_DMA_DOMAIN_CREATION_FLAGS
 - PIOMMU_DMA_DOMAIN_CREATION_FLAGS
 - wdm/PIOMMU_DMA_DOMAIN_CREATION_FLAGS
 - IOMMU_DMA_DOMAIN_CREATION_FLAGS
 - wdm/IOMMU_DMA_DOMAIN_CREATION_FLAGS
dev_langs:
 - c++
---

## -description

The **IOMMU_DMA_DOMAIN_CREATION_FLAGS** structure defines configuration flags for a domain being created by [**IOMMU_DOMAIN_CREATE_EX**](nc-wdm-iommu_domain_create_ex.md).

## -struct-fields

### -field Reserved

All flags are currently reserved. This field must be zero.

### -field AsUlonglong

Represents all flags as a single **ULONGLONG**.

## -remarks

Currently the flags are unused and must be all zero when passed in to [**IOMMU_DOMAIN_CREATE_EX**](nc-wdm-iommu_domain_create_ex.md).

## -see-also

[**IOMMU_DOMAIN_CREATE_EX**](nc-wdm-iommu_domain_create_ex.md)
