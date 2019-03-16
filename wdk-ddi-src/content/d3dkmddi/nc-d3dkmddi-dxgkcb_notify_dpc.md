---
UID: NC:d3dkmddi.DXGKCB_NOTIFY_DPC
title: DXGKCB_NOTIFY_DPC (d3dkmddi.h)
description: The DxgkCbNotifyDpc function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at deferred-procedure-call (DPC) time.
old-location: display\dxgkcbnotifydpc.htm
ms.assetid: 3df3f7d4-3721-46f5-b9e3-19bd3d870292
ms.date: 05/10/2018
ms.keywords: DXGKCB_NOTIFY_DPC, DXGKCB_NOTIFY_DPC callback, DpFunctions_a1e9512a-ae77-4e3b-9876-5ce247b811e5.xml, DxgkCbNotifyDpc, DxgkCbNotifyDpc callback function [Display Devices], d3dkmddi/DxgkCbNotifyDpc, display.dxgkcbnotifydpc
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3dkmddi.h
api_name:
- DxgkCbNotifyDpc
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_NOTIFY_DPC callback function


## -description


The <b>DxgkCbNotifyDpc</b> function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at deferred-procedure-call (DPC) time.


## -parameters




### -param hAdapter [in]

[in] A handle to the adapter object for the GPU. The driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


## -returns



None




## -remarks



The display miniport driver's DPC callback routine calls the <b>DxgkCbNotifyDpc</b> function to inform the GPU scheduler about an update to a fence through a direct memory access (DMA) stream to the graphics hardware. 


#### Examples

The following code example shows how to notify the GPU scheduler about the DMA or V-Sync interrupt.

```cpp
NTSTATUS
D3DDDINotifyDPC(
    HW_DEVICE_EXTENSION  *pAdapter)
{
    DXGKRNL_INTERFACE  *pCallback;
    DXGKCB_NOTIFY_DPC  DxgkCbNotifyDpc;

    pCallback = &amp;(pAdapter-&gt;ddiCallback);

    if (! pAdapter-&gt;pVidSchDPCCB) {
        return (STATUS_SUCCESS);
    }

    DxgkCbNotifyDpc = (DXGKCB_NOTIFY_DPC)pAdapter-&gt;pVidSchDPCCB;

    DxgkCbNotifyDpc(pAdapter-&gt;DeviceHandle);

    return (STATUS_SUCCESS);
}
```



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a>



<a href="https://msdn.microsoft.com/c8c26675-8b87-4818-ad51-4e0a341965d0">DxgkCbQueueDpc</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>
 

 

