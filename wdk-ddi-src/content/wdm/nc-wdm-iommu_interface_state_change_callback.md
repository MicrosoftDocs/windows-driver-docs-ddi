---
UID: NC:wdm.IOMMU_INTERFACE_STATE_CHANGE_CALLBACK
tech.root: kernel
title: IOMMU_INTERFACE_STATE_CHANGE_CALLBACK
ms.date: 06/04/2021
targetos: Windows
description: This routine is invoked whenever there has been a system state change that affects a DMA_IOMMU_INTERFACE_EX.
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
 - IOMMU_INTERFACE_STATE_CHANGE_CALLBACK
f1_keywords:
 - IOMMU_INTERFACE_STATE_CHANGE_CALLBACK
 - wdm/IOMMU_INTERFACE_STATE_CHANGE_CALLBACK
dev_langs:
 - c++
---

## -description

This routine is invoked whenever there has been a system state change that affects a [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md).

## -parameters

### -param StateChange

[*In*] A pointer to the state information that indicates which states have changed. See [**IOMMU_INTERFACE_STATE_CHANGE**](ns-wdm-iommu_interface_state_change.md).

### -param Context

[*In*, optional] An optional caller-specified context that matches the optional context passed in when registering an IOMMU Interface state change callback through [**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md).

## -remarks

This callback should be registered via [**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md). It will be immediately invoked upon registration (to avoid race conditions) and whenever a system state change has occurred. The callback owner should not assume the state and should always check the provided state information in [**IOMMU_INTERFACE_STATE_CHANGE**](ns-wdm-iommu_interface_state_change.md).

It is the callback owner's responsibility to unregister the callback, using [**IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_unregister_interface_state_change_callback.md), before disposing of an [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md) or **IOMMU_DMA_DEVICE**.

## -see-also

[**IOMMU_INTERFACE_STATE_CHANGE**](ns-wdm-iommu_interface_state_change.md)

[**IOMMU_INTERFACE_STATE_CHANGE_FIELDS**](ns-wdm-iommu_interface_state_change_fields.md)

[**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md)

[**IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_unregister_interface_state_change_callback.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
