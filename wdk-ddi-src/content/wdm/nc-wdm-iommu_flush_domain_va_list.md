---
UID: NC:wdm.IOMMU_FLUSH_DOMAIN_VA_LIST
title: IOMMU_FLUSH_DOMAIN_VA_LIST
author: windows-driver-content
description: Flushes the TLB for all entries that match the specified domain's ASID and one of the addresses in the provided list. 
ms.assetid: 3ae0eb66-ed0d-4232-9294-4037ae48ce3e
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
-	IOMMU_FLUSH_DOMAIN_VA_LIST
product:
-	Windows
targetos: Windows
---

# IOMMU_FLUSH_DOMAIN_VA_LIST callback function

## -description

Flushes the TLB for all entries that match the specified domain's ASID and one of the addresses in the provided list. 

## -prototype

```
//Declaration

IOMMU_FLUSH_DOMAIN_VA_LIST IommuFlushDomainVaList; 

// Definition

NTSTATUS IommuFlushDomainVaList 
(
	PIOMMU_DMA_DOMAIN Domain
	BOOLEAN LastLevel
	ULONG Number
	PVOID VaList
)
{...}

IOMMU_FLUSH_DOMAIN_VA_LIST *PIOMMU_FLUSH_DOMAIN_VA_LIST


```

## -parameters

### -param Domain
[_In_] A pointer to the handle to the domain.
 
### -param LastLevel
[_In_] A boolean value that indicates whether only entries pertaining to the last level of translation require flushing.

### -param Number
[_In_] The number of entries in the VA list.

### -param VaList 
[_In_] A pointer to a list of flush addresses.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code. For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks


## -see-also