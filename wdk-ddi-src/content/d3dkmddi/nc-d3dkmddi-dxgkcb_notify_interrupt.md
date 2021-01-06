---
UID: NC:d3dkmddi.DXGKCB_NOTIFY_INTERRUPT
title: DXGKCB_NOTIFY_INTERRUPT (d3dkmddi.h)
description: The DxgkCbNotifyInterrupt function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at interrupt-service-routine (ISR) time.
old-location: display\dxgkcbnotifyinterrupt.htm
ms.date: 05/10/2018
keywords: ["DXGKCB_NOTIFY_INTERRUPT callback function"]
ms.keywords: DXGKCB_NOTIFY_INTERRUPT, DXGKCB_NOTIFY_INTERRUPT callback, DpFunctions_fdb60c96-9eec-4e57-a4bd-1b97ad99769b.xml, DxgkCbNotifyInterrupt, DxgkCbNotifyInterrupt callback function [Display Devices], d3dkmddi/DxgkCbNotifyInterrupt, display.dxgkcbnotifyinterrupt
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
req.irql: See Remarks section.
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_NOTIFY_INTERRUPT
 - d3dkmddi/DXGKCB_NOTIFY_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DxgkCbNotifyInterrupt
product:
 - Windows
---

# DXGKCB_NOTIFY_INTERRUPT callback function


## -description

The <b>DxgkCbNotifyInterrupt</b> function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at interrupt-service-routine (ISR) time.

## -parameters

### -param hAdapter

[in] A handle to the adapter object for the GPU. A driver receives the handle from the <b>DeviceHandle</b> member of the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure in a call to its <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

## -remarks

A display miniport driver calls the <b>DxgkCbNotifyInterrupt</b> function to report a graphics hardware interrupt that the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_interrupt_type">DXGK_INTERRUPT_TYPE</a> enumeration type defines. Typically, <b>DxgkCbNotifyInterrupt</b> is called from the display miniport driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_interrupt_routine">DxgkDdiInterruptRoutine</a> function (ISR), which is called when graphics hardware interrupts occur. The <b>DxgkCbNotifyInterrupt</b> function informs the GPU scheduler about an update to a fence through a direct memory access (DMA) stream to the graphics hardware. 

If the display miniport driver uses multiple interrupt handlers that correspond to multiple IRQLs, the driver must not call <b>DxgkCbNotifyInterrupt</b> in a reentrant fashion. Therefore, in this case, the display miniport driver should always call <b>DxgkCbNotifyInterrupt</b> from a fixed level of the interrupt handler. 

Similarly, if message-signaled interrupts are used, the display miniport driver can call <b>DxgkCbNotifyInterrupt</b> from an interrupt handler that corresponds to a fixed message number. The driver must report the message number that is used for notification in the <b>InterruptMessageNumber</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a> structure, when the DXGKQAITYPE_DRIVERCAPS enumeration value is specified in the <b>Type</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a> structure in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

After the display miniport driver calls <b>DxgkCbNotifyInterrupt</b> but before the driver exits its ISR, the driver must queue a deferred procedure call (DPC) by using the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_queue_dpc">DxgkCbQueueDpc</a> function. This DPC must be queued because the GPU scheduler must also be notified, when the driver's DPC callback routine calls the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a> function, about the same event at DPC time. A certain amount of processing that is related to graphics hardware events can be only performed by the operating system at DPC time. 

If the display miniport driver determines that more than one interrupt was triggered in hardware and the driver must call <b>DxgkCbNotifyInterrupt</b> for each interrupt to report the interrupt to the operating system, the driver should report DMA-type interrupts before a CRTC-type interrupt. For more information about interrupt types, see the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_interrupt_type">DXGK_INTERRUPT_TYPE</a> reference page.

Callers of <b>DxgkCbNotifyInterrupt</b> run at interrupt level (that is, DIRQL, which is some IRQL between DISPATCH_LEVEL and PROFILE_LEVEL, not inclusive).


#### Examples

The following code example shows software engine code that monitors a software queue and notifies the GPU scheduler about packet completion.

```cpp
typedef struct _SubmitParams {
    HW_DEVICE_EXTENSION *pHwDeviceExtension;
    UINT                NodeOrdinal;
    UINT                FenceID;
    UINT                PreemptionFenceID;
} SubmitParams;

BOOLEAN R200TEST_SWNode_SynchronizeVidSchNotifyInt(PVOID* params)
{
    SubmitParams  *pSchNotifyParams = (SubmitParams*)params;
    DXGKCB_NOTIFY_INTERRUPT  DxgkCbNotifyInterrupt;
    DXGKARGCB_NOTIFY_INTERRUPT_DATA  notifyInt = {0};

    DxgkCbNotifyInterrupt = (DXGKCB_NOTIFY_INTERRUPT)pSchNotifyParams->pHwDeviceExtension->pVidSchINTCB;

    if(!DxgkCbNotifyInterrupt) {
        return FALSE;
    }

    if(pSchNotifyParams->PreemptionFenceID) {
        notifyInt.InterruptType = DXGK_INTERRUPT_DMA_PREEMPTED;
        notifyInt.DmaPreempted.PreemptionFenceId = pSchNotifyParams->PreemptionFenceID;
        notifyInt.DmaPreempted.LastCompletedFenceId = pSchNotifyParams->FenceID;
        notifyInt.DmaPreempted.NodeOrdinal = pSchNotifyParams->NodeOrdinal;
    }
    else {
        notifyInt.InterruptType = DXGK_INTERRUPT_DMA_COMPLETED;
        notifyInt.DmaCompleted.SubmissionFenceId = pSchNotifyParams->FenceID;
        notifyInt.DmaCompleted.NodeOrdinal = pSchNotifyParams->NodeOrdinal;
    }

    DxgkCbNotifyInterrupt(pSchNotifyParams->pHwDeviceExtension->DeviceHandle, &notifyInt);

    pSchNotifyParams->pHwDeviceExtension->PrevSubmitFenceIDArray[pSchNotifyParams->NodeOrdinal] = pSchNotifyParams->FenceID;

    if(pSchNotifyParams->PreemptionFenceID) {
        pSchNotifyParams->pHwDeviceExtension->PrevPreemptFenceIDArray[pSchNotifyParams->NodeOrdinal] = pSchNotifyParams->PreemptionFenceID;
    }

    return TRUE;
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_notify_interrupt_data">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ne-d3dkmddi-_dxgk_interrupt_type">DXGK_INTERRUPT_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_queue_dpc">DxgkCbQueueDpc</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_interrupt_routine">DxgkDdiInterruptRoutine</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>
