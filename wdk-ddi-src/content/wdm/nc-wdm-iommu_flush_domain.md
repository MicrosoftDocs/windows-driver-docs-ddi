---
UID: NC:wdm.IOMMU_FLUSH_DOMAIN
title: IOMMU_FLUSH_DOMAIN (wdm.h)
description: Flushes the TLB for all entries which match this domain.
ms.assetid: 00bc433e-f306-485e-bc78-cab66cab879e
ms.date: 10/19/2018
keywords: ["IOMMU_FLUSH_DOMAIN callback function"]
f1_keywords:
 - "wdm/IOMMU_FLUSH_DOMAIN"
 - "IOMMU_FLUSH_DOMAIN"
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
- IOMMU_FLUSH_DOMAIN
product:
- Windows
targetos: Windows
---

# IOMMU_FLUSH_DOMAIN callback function

## -description

Flushes the TLB for all entries which match this domain. 

## -prototype

```cpp
//Declaration

IOMMU_FLUSH_DOMAIN IommuFlushDomain; 

// Definition

NTSTATUS IommuFlushDomain 
(
	PIOMMU_DMA_DOMAIN Domain
)
{...}

IOMMU_FLUSH_DOMAIN *PIOMMU_FLUSH_DOMAIN


```

## -parameters

### -param Domain 
[_In_] A pointer to the handle to the domain.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks




## -see-also
