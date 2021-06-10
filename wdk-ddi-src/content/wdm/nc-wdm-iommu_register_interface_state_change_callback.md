---
UID: NC:wdm.IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK
tech.root: kernel
title: IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK
ms.date: 06/04/2021
targetos: Windows
description: Allows the caller to register a callback to be invoked whenever any state change related to a DMA_IOMMU_INTERFACE_EX occurs.
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
 - IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK
f1_keywords:
 - IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK
 - wdm/IOMMU_REGISTER_INTERFACE_STATE_CHANGE_CALLBACK
dev_langs:
 - c++
---

## -description

Allows the caller to register a callback to be invoked whenever any state change related to a [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md) occurs.

## -parameters

### -param StateChangeCallback

[*In*]
The [**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md) to be registered.

### -param Context

[*In*, optional]
An optional context that will be passed to the state change callback.

### -param DmaDevice

[*In*]
A pointer to an opaque token representing the **IOMMU_DMA_DEVICE** that will be linked to the callback.

### -param StateFields

[*In*]
A pointer to the states that a caller is registering to be notified about. See [**IOMMU_INTERFACE_STATE_CHANGE_FIELDS**](ns-wdm-iommu_interface_state_change_fields.md).

## -returns

**STATUS_SUCCESS** if the operation is successful.

Possible error return values include the following status codes.

| Return code | Description |
|--|--|
| STATUS_UNSUCCESSFUL | The routine failed to register the provided callback because the **IOMMU_DMA_DEVICE** has already been registered with a callback. |
| STATUS_INVALID_PARAMETER_4 | The caller did not indicate interest in any interface state field in `StateFields`. |

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

Registration will always immediately invoke the callback to avoid race conditions with any notifications that invoke the callbacks. Callback owners should not assume the state when a callback is invoked and should always check that the state matches their needs.

Before disposing of a [**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md) or **IOMMU_DMA_DEVICE**, the owner is responsible for unregistering all its registered callbacks.

Only one callback can be registered per **IOMMU_DMA_DEVICE**.

## -see-also

[**DMA_IOMMU_INTERFACE_V2**](ns-wdm-dma_iommu_interface_v2.md)

[**DMA_IOMMU_INTERFACE_EX**](ns-wdm-dma_iommu_interface_ex.md)

[**IOMMU_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_interface_state_change_callback.md)

[**IOMMU_INTERFACE_STATE_CHANGE_FIELDS**](ns-wdm-iommu_interface_state_change_fields.md)

[**IOMMU_UNREGISTER_INTERFACE_STATE_CHANGE_CALLBACK**](nc-wdm-iommu_unregister_interface_state_change_callback.md)
