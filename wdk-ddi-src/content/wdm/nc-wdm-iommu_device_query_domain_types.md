---
UID: NC:wdm.IOMMU_DEVICE_QUERY_DOMAIN_TYPES
tech.root: kernel
title: IOMMU_DEVICE_QUERY_DOMAIN_TYPES
ms.date: 06/04/2021
targetos: Windows
description: Queries for the available types of domains that a IOMMU_DMA_DEVICE is allowed to attach to, depending on environment factors, such as platform and DMA Guard Policy.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - wdm.h
api_name:
 - IOMMU_DEVICE_QUERY_DOMAIN_TYPES
f1_keywords:
 - IOMMU_DEVICE_QUERY_DOMAIN_TYPES
 - wdm/IOMMU_DEVICE_QUERY_DOMAIN_TYPES
dev_langs:
 - c++
---

## -description

Queries for the available types of domains that an **IOMMU_DMA_DEVICE** is allowed to attach to, depending on environment factors, such as platform and DMA Guard Policy.

## -parameters

### -param DmaDevice

[*In*] A pointer to an opaque token representing the **IOMMU_DMA_DEVICE**.

### -param AvailableDomains

[*Out*] Returns the current domain types that are available to be created and attached to. Each set bit represents an available domain type: `(1 << IOMMU_DMA_DOMAIN_TYPE)`. See [**IOMMU_DMA_DOMAIN_TYPE**](ne-wdm-iommu_dma_domain_type.md).

## -remarks

This can be used as a hint as to whether [**IOMMU_DOMAIN_ATTACH_DEVICE_EX**](nc-wdm-iommu_domain_attach_device_ex.md) will succeed.

If a device is not behind a DMA remapping compatible IOMMU, then no remapping domain will be available.

If DMA Guard is enabled, then passthrough domains may be available based on policy, i.e. whether the device is opted into DMA remapping, is connected externally, the screen lock state, etc.. If DMA Guard blocking is active, then passthrough domains will not be available and `AvailableDomains & (1 << DomainTypePassThrough)` will result in 0.

To be notified of when domain types are available, consider using [**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md) to register a notification callback whenever the available domain types change.

## -see-also

[**IOMMU_DMA_DOMAIN_TYPE**](ne-wdm-iommu_dma_domain_type.md)

[**IOMMU_DOMAIN_ATTACH_DEVICE_EX**](nc-wdm-iommu_domain_attach_device_ex.md)

[**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
