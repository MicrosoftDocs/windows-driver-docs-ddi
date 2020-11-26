---
UID: NC:wdm.IOMMU_DOMAIN_FAULT_HANDLER
title: IOMMU_DOMAIN_FAULT_HANDLER (wdm.h)
description: Sets the fault report on a device that is already attached to a domain.
ms.assetid: bf44815d-9a0b-482b-8525-816a98c727f9
ms.date: 10/19/2018
tech.root: kernel
keywords: ["IOMMU_DOMAIN_FAULT_HANDLER callback function"]
f1_keywords:
 - "wdm/IOMMU_DOMAIN_FAULT_HANDLER"
 - "IOMMU_DOMAIN_FAULT_HANDLER"
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
- IOMMU_DOMAIN_FAULT_HANDLER
targetos: Windows
---

# IOMMU_DOMAIN_FAULT_HANDLER callback function

## -description

Sets the fault report on a device that is already attached to a domain.

## -prototype

```cpp
//Declaration

IOMMU_DOMAIN_FAULT_HANDLER IommuDomainFaultHandler;

// Definition

VOID IommuDomainFaultHandler
(
    PVOID Context
    PFAULT_INFORMATION FaultInformation
)
{...}

IOMMU_DOMAIN_FAULT_HANDLER *PIOMMU_DOMAIN_FAULT_HANDLER


```

## -parameters

### -param Context

A pointed to the driver-supplied context.

### -param FaultInformation

A pointer to a [**FAULT_INFORMATION**](ns-wdm-_fault_information.md) structure that contains the fault report.

## -returns

## -remarks

## -see-also
