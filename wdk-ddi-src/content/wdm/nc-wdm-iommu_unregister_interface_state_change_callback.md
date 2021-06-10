---
UID: NC:wdm.IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK
tech.root: kernel
title: IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK
ms.date: 06/04/2021
targetos: Windows
description: Allows the caller to deregister a registered IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK.
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
 - IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK
f1_keywords:
 - IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK
 - wdm/IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK
dev_langs:
 - c++
---

## -description

Allows the caller to deregister a registered [**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md).

## -parameters

### -param StateChangeCallback

[*In*]
The [**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md) to be unregistered.

### -param DmaDevice

[*In*]
A pointer to an opaque token representing the **IOMMU_DMA_DEVICE** associated with the provided callback.

## -returns

**STATUS_SUCCESS** if the operation is successful.

Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| STATUS_UNSUCCESSFUL | The provided [**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md) is not a registered callback. |

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Before disposing of a [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md) or **IOMMU_DMA_DEVICE**, the owner is responsible for unregistering all its registered callbacks.

Only one callback can be registered per **IOMMU_DMA_DEVICE**.

## -see-also

[**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md)

[**IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_register_interface_state_change_callback.md)

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)
