---
UID: NC:wdm.IOMMU_MAP_LOGICAL_RANGE
title: IOMMU_MAP_LOGICAL_RANGE (wdm.h)
description: Maps a range of pages into the address space of a domain.
tech.root: kernel
ms.date: 10/19/2018
keywords: ["IOMMU_MAP_LOGICAL_RANGE callback function"]
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
 - IOMMU_MAP_LOGICAL_RANGE
 - wdm/IOMMU_MAP_LOGICAL_RANGE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - wdm.h
api_name:
 - IOMMU_MAP_LOGICAL_RANGE
---

# IOMMU_MAP_LOGICAL_RANGE callback function


## -description

Maps a range of pages into the address space of the specified domain.

## -parameters

### -param Domain

[_In_] A pointer to the handle to the domain.

### -param Permissions

[_In_] A ULONG variable that specifies the permissions with which to map the pages.

### -param Mdl

[_In_] A pointer to the MDL to map. The provided MDL must specify a whole number of page.

### -param LogicalAddress

[_In_] The logical address at which mapping begins. The address must be page aligned.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -prototype

```cpp
//Declaration

IOMMU_MAP_LOGICAL_RANGE IommuMapLogicalRange; 

// Definition

NTSTATUS IommuMapLogicalRange 
(
	PIOMMU_DMA_DOMAIN Domain
	ULONG Permissions
	PMDL Mdl
	ULONGLONG LogicalAddress
)
{...}

IOMMU_MAP_LOGICAL_RANGE *PIOMMU_MAP_LOGICAL_RANGE


```

## -remarks

## -see-also
