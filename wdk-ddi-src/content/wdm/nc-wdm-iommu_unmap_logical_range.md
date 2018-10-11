---
UID: NC:wdm.IOMMU_UNMAP_LOGICAL_RANGE
title: IOMMU_UNMAP_LOGICAL_RANGE
author: windows-driver-content
description: Unmaps a linear range from a domain.
ms.assetid: 48b802b6-980c-407b-91cc-02b67c80fdc5
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IOMMU_UNMAP_LOGICAL_RANGE
product:
-	Windows
targetos: Windows
---

# IOMMU_UNMAP_LOGICAL_RANGE callback function

## -description

Unmaps a linear range from a domain. 

## -prototype

```
//Declaration

IOMMU_UNMAP_LOGICAL_RANGE IommuUnmapLogicalRange; 

// Definition

NTSTATUS IommuUnmapLogicalRange 
(
	PIOMMU_DMA_DOMAIN Domain
	ULONGLONG LogicalAddress
	ULONGLONG NumberOfPages
)
{...}

IOMMU_UNMAP_LOGICAL_RANGE *PIOMMU_UNMAP_LOGICAL_RANGE


```

## -parameters

### -param Domain
[_In_] A pointer to the handle to the domain.

### -param LogicalAddress
[_In_] The logical address at which unmapping begins. The address must be page aligned.

### -param NumberOfPages
[_In_] The number of pages to unmap.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks


## -see-also