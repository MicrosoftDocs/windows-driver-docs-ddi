---
UID: NC:wdm.IOMMU_MAP_IDENTITY_RANGE
title: IOMMU_MAP_IDENTITY_RANGE (wdm.h)
description: Creates an identity mapping for the provided MDL in the provided domain.
ms.assetid: cdd44fd5-20c2-488a-bfcb-001f1b4490cb
ms.date: 10/19/2018
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location:
- wdm.h
api_name: 
- IOMMU_MAP_IDENTITY_RANGE
product:
- Windows
targetos: Windows
---

# IOMMU_MAP_IDENTITY_RANGE callback function

## -description

Creates an identity mapping for the provided MDL in the specified domain. 

## -prototype

```cpp
//Declaration

IOMMU_MAP_IDENTITY_RANGE IommuMapIdentityRange; 

// Definition

NTSTATUS IommuMapIdentityRange 
(
	PIOMMU_DMA_DOMAIN Domain
	ULONG Permissions
	PMDL Mdl
)
{...}

IOMMU_MAP_IDENTITY_RANGE *PIOMMU_MAP_IDENTITY_RANGE


```

## -parameters

### -param Domain
[_In_] A pointer to the handle to the domain.
 
### -param Permissions
[_In_] A ULONG variable that specifies the permissions for the mapping.
 
### -param Mdl
[_In_] A pointer to the MDL to map.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks



## -see-also
