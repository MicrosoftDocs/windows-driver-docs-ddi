---
UID: NC:wdm.IOMMU_SET_DEVICE_FAULT_REPORTING_EX
tech.root: kernel
title: IOMMU_SET_DEVICE_FAULT_REPORTING_EX
ms.date: 06/04/2021
targetos: Windows
description: This routine set the device fault reporting state on a device already attached to a domain.
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
 - IOMMU_SET_DEVICE_FAULT_REPORTING_EX
f1_keywords:
 - IOMMU_SET_DEVICE_FAULT_REPORTING_EX
 - wdm/IOMMU_SET_DEVICE_FAULT_REPORTING_EX
dev_langs:
 - c++
---

## -description

This routine set the device fault reporting state on a device already attached to a domain.

## -parameters

### -param DmaDevice

[*In*] A pointer to the **IOMMU_DMA_DEVICE**.

### -param InputMappingIdBase

[*In*] The base input mapping ID for the device.

### -param Enable

[*In*] A **BOOLEAN** indicating whether to enable fault reporting for the device.

### -param FaultConfig

[*In*, optional] An optional pointer to [**DEVICE_FAULT_CONFIGURATION**](ns-wdm-_device_fault_configuration.md). Only used when enabling fault reporting.

## -returns

**STATUS_NOT_IMPLEMENTED** always.

## -remarks

This is currently not implemented and will return as such.

## -see-also

[**IOMMU_DOMAIN_ATTACH_DEVICE_EX**](nc-wdm-iommu_domain_attach_device_ex.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
