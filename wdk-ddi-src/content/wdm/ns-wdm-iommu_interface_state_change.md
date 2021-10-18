---
UID: NS:wdm._IOMMU_INTERFACE_STATE_CHANGE
tech.root: kernel
title: IOMMU_INTERFACE_STATE_CHANGE
ms.date: 04/20/2021
targetos: Windows
description: "Learn more about: IOMMU_INTERFACE_STATE_CHANGE"
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: IOMMU_INTERFACE_STATE_CHANGE, *PIOMMU_INTERFACE_STATE_CHANGE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _IOMMU_INTERFACE_STATE_CHANGE
 - PIOMMU_INTERFACE_STATE_CHANGE
 - IOMMU_INTERFACE_STATE_CHANGE
f1_keywords:
 - _IOMMU_INTERFACE_STATE_CHANGE
 - wdm/_IOMMU_INTERFACE_STATE_CHANGE
 - PIOMMU_INTERFACE_STATE_CHANGE
 - wdm/PIOMMU_INTERFACE_STATE_CHANGE
 - IOMMU_INTERFACE_STATE_CHANGE
 - wdm/IOMMU_INTERFACE_STATE_CHANGE
dev_langs:
 - c++
---

## -description

**IOMMU_INTERFACE_STATE_CHANGE** represents the IOMMU interface state at the time a state change callback is invoked. When an [**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md) is invoked, the `PresentFields` indicate which [**IOMMU_INTERFACE_STATE_CHANGE_FIELDS**](ns-wdm-iommu_interface_state_change_fields.md) have changed while the rest of the members of **IOMMU_INTERFACE_STATE_CHANGE** provide the new state.

## -struct-fields

### -field PresentFields

Indicates which IOMMU interface states have changed. If a field within this structure is set to 1, this indicates a state change for that state field.

### -field AvailableDomainTypes

Represents all the domain types currently available. Each set bit represents an available domain type: `(1 << IOMMU_DMA_DOMAIN_TYPE)`. See [**IOMMU_DMA_DOMAIN_TYPE**](ne-wdm-iommu_dma_domain_type.md) for more details.

## -remarks

## -see-also

[**IOMMU_INTERFACE_STATE_CHANGE_FIELDS**](ns-wdm-iommu_interface_state_change_fields.md)

[**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md)

[**IOMMU_DMA_DOMAIN_TYPE**](ne-wdm-iommu_dma_domain_type.md)
