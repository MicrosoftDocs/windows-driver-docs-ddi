---
UID: NC:wdm.IOMMU_UNMAP_IDENTITY_RANGE
title: IOMMU_UNMAP_IDENTITY_RANGE (wdm.h)
description: Deletes an identity mapping for the specified MDL.
tech.root: kernel
ms.date: 10/19/2018
keywords: ["IOMMU_UNMAP_IDENTITY_RANGE callback function"]
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
targetos: Windows
f1_keywords:
 - IOMMU_UNMAP_IDENTITY_RANGE
 - wdm/IOMMU_UNMAP_IDENTITY_RANGE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - IOMMU_UNMAP_IDENTITY_RANGE
---

# IOMMU_UNMAP_IDENTITY_RANGE callback function


## -description

Deletes an identity mapping for the specified MDL.

## -parameters

### -param Domain

[_In_] A pointer to the handle to the domain.

### -param Mdl

[_In_] A pointer to the MDL to unmap.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -prototype

```cpp
//Declaration

IOMMU_UNMAP_IDENTITY_RANGE IommuUnmapIdentityRange; 

// Definition

NTSTATUS IommuUnmapIdentityRange 
(
	PIOMMU_DMA_DOMAIN Domain
	PMDL Mdl
)
{...}

IOMMU_UNMAP_IDENTITY_RANGE *PIOMMU_UNMAP_IDENTITY_RANGE


```

## -remarks

## -see-also
