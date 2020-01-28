---
UID: NC:dispmprt.DXGKCB_QUEUE_DPC
title: DXGKCB_QUEUE_DPC (dispmprt.h)
description: The DxgkCbQueueDpc function queues a deferred procedure call (DPC) for execution at IRQL DISPATCH_LEVEL.
old-location: display\dxgkcbqueuedpc.htm
tech.root: display
ms.assetid: c8c26675-8b87-4818-ad51-4e0a341965d0
ms.date: 05/10/2018
ms.keywords: DXGKCB_QUEUE_DPC, DXGKCB_QUEUE_DPC callback, DpFunctions_0d1685f8-bd6f-45cc-a958-54330281a44f.xml, DxgkCbQueueDpc, DxgkCbQueueDpc callback function [Display Devices], display.dxgkcbqueuedpc, dispmprt/DxgkCbQueueDpc
f1_keywords:
 - "dispmprt/DxgkCbQueueDpc"
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dispmprt.h
api_name:
- DxgkCbQueueDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# DXGKCB_QUEUE_DPC callback function


## -description


The <b>DxgkCbQueueDpc</b> function queues a deferred procedure call (DPC) for execution at IRQL  DISPATCH_LEVEL.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>.


## -returns



<b>DxgkCbQueueDpc</b> returns <b>TRUE</b> if the DPC is successfully queued; otherwise it returns <b>FALSE</b>.




## -remarks



This function queues a DPC object for the display miniport and calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_dpc_routine">DxgkDdiDpcRoutine</a> function when the interrupt service routine (ISR) requests it. 

There can only be one callback to this function scheduled per device at any one time. If a callback is already scheduled for a device, a second call to <b>DxgkCbQueueDpc</b> will not have any effect and will return <b>FALSE</b>.

For more information on the use of this function, see these topics:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/display/submitting-a-command-buffer">Submitting a Command Buffer</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/display/windows-vista-and-later-display-driver-model-operation-flow">Windows Display Driver Model (WDDM) Operation Flow</a>
</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_queue_dpc">DxgkCbQueueDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_dpc_routine">DxgkDdiDpcRoutine</a>
 

 

