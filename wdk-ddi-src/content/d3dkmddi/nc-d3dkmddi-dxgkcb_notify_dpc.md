---
UID: NC:d3dkmddi.DXGKCB_NOTIFY_DPC
title: DXGKCB_NOTIFY_DPC (d3dkmddi.h)
description: The DxgkCbNotifyDpc function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at deferred-procedure-call (DPC) time.
old-location: display\dxgkcbnotifydpc.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_NOTIFY_DPC callback function"]
ms.keywords: DXGKCB_NOTIFY_DPC, DXGKCB_NOTIFY_DPC callback, DpFunctions_a1e9512a-ae77-4e3b-9876-5ce247b811e5.xml, DxgkCbNotifyDpc, DxgkCbNotifyDpc callback function [Display Devices], d3dkmddi/DxgkCbNotifyDpc, display.dxgkcbnotifydpc
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_NOTIFY_DPC
 - d3dkmddi/DXGKCB_NOTIFY_DPC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_NOTIFY_DPC
product:
 - Windows
---

# DXGKCB_NOTIFY_DPC callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_NOTIFY_DPC** to inform the graphics processing unit (GPU) scheduler about a graphics hardware update at deferred procedure call (DPC) time.

## -parameters

### -param hAdapter

[in] A handle to the adapter object for the GPU. The driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

## -remarks

The display miniport driver's DPC callback routine calls **DXGKCB_NOTIFY_DPC** to inform the GPU scheduler about an update to a fence through a direct memory access (DMA) stream to the graphics hardware.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbNotifyDpc** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

### Examples

The following code example shows how to notify the GPU scheduler about the DMA or V-Sync interrupt.

```cpp
NTSTATUS
D3DDDINotifyDPC(
    HW_DEVICE_EXTENSION  *pAdapter)
{
    DXGKRNL_INTERFACE  *pCallback;
    DXGKCB_NOTIFY_DPC  DxgkCbNotifyDpc;

    pCallback = &(pAdapter->ddiCallback);

    if (! pAdapter->pVidSchDPCCB) {
        return (STATUS_SUCCESS);
    }

    DxgkCbNotifyDpc = (DXGKCB_NOTIFY_DPC)pAdapter->pVidSchDPCCB;

    DxgkCbNotifyDpc(pAdapter->DeviceHandle);

    return (STATUS_SUCCESS);
}
```

## -see-also

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)

[**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)

[**DxgkCbQueueDpc**](../dispmprt/nc-dispmprt-dxgkcb_queue_dpc.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
