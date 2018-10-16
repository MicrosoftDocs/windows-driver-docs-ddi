---
UID: NC:wdm.IOMMU_DOMAIN_CREATE
title: IOMMU_DOMAIN_CREATE
author: windows-driver-content
description: Creates a new DMA remapping device domain (a container for a set of page tables).
ms.assetid: 70cce6f5-5adb-4646-b98d-e42d8e8f0389
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
-	IOMMU_DOMAIN_CREATE
product:
-	Windows
targetos: Windows
---

# IOMMU_DOMAIN_CREATE callback function

## -description

Creates a new DMA remapping device domain (a container for a set of page tables).

## -prototype

```cpp
//Declaration

IOMMU_DOMAIN_CREATE IommuDomainCreate; 

// Definition

NTSTATUS IommuDomainCreate 
(
	BOOLEAN OsManagedPageTable
	PIOMMU_DMA_DOMAIN * DomainOut
)
{...}

IOMMU_DOMAIN_CREATE *PIOMMU_DOMAIN_CREATE


```

## -parameters

### -param OsManagedPageTable
[_In_] A boolean value that indicates whether the page table is managed by the caller or by the HAL. 

-    TRUE, indicates the HAL owns the page table. 
        - Map/Unmap are available.      
        - Configure/Flush are unavailable.

- FALSE indicates that the caller owns the page table.
    - Map/Unmap are unavailable.
    - Configure/Flush are available.

### -param DomainOut: 
[_Out_] A pointer to IOMMU_DMA_DOMAIN variable that receives an opaque handle used to reference the domain.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks



## -see-also
