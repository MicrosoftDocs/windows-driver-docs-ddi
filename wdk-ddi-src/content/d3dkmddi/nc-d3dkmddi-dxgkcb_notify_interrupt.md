---
UID: NC:d3dkmddi.DXGKCB_NOTIFY_INTERRUPT
title: DXGKCB_NOTIFY_INTERRUPT
author: windows-driver-content
description: The DxgkCbNotifyInterrupt function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at interrupt-service-routine (ISR) time.
old-location: display\dxgkcbnotifyinterrupt.htm
ms.assetid: 7968d26d-0195-463d-8954-e7ebef4f9dea
ms.date: 5/10/2018
ms.keywords: DXGKCB_NOTIFY_INTERRUPT, DXGKCB_NOTIFY_INTERRUPT callback, DpFunctions_fdb60c96-9eec-4e57-a4bd-1b97ad99769b.xml, DxgkCbNotifyInterrupt, DxgkCbNotifyInterrupt callback function [Display Devices], d3dkmddi/DxgkCbNotifyInterrupt, display.dxgkcbnotifyinterrupt
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkCbNotifyInterrupt
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_NOTIFY_INTERRUPT callback function


## -description


The <b>DxgkCbNotifyInterrupt</b> function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at interrupt-service-routine (ISR) time.


## -parameters




### -param hAdapter 

[in] A handle to the adapter object for the GPU. A driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


## -returns



None




## -remarks



A display miniport driver calls the <b>DxgkCbNotifyInterrupt</b> function to report a graphics hardware interrupt that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561136">DXGK_INTERRUPT_TYPE</a> enumeration type defines. Typically, <b>DxgkCbNotifyInterrupt</b> is called from the display miniport driver's <a href="https://msdn.microsoft.com/eacfd42d-405c-4c23-8978-0f373a393e10">DxgkDdiInterruptRoutine</a> function (ISR), which is called when graphics hardware interrupts occur. The <b>DxgkCbNotifyInterrupt</b> function informs the GPU scheduler about an update to a fence through a direct memory access (DMA) stream to the graphics hardware. 

If the display miniport driver uses multiple interrupt handlers that correspond to multiple IRQLs, the driver must not call <b>DxgkCbNotifyInterrupt</b> in a reentrant fashion. Therefore, in this case, the display miniport driver should always call <b>DxgkCbNotifyInterrupt</b> from a fixed level of the interrupt handler. 

Similarly, if message-signaled interrupts are used, the display miniport driver can call <b>DxgkCbNotifyInterrupt</b> from an interrupt handler that corresponds to a fixed message number. The driver must report the message number that is used for notification in the <b>InterruptMessageNumber</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a> structure, when the DXGKQAITYPE_DRIVERCAPS enumeration value is specified in the <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a> structure in a call to the driver's <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.

After the display miniport driver calls <b>DxgkCbNotifyInterrupt</b> but before the driver exits its ISR, the driver must queue a deferred procedure call (DPC) by using the <a href="https://msdn.microsoft.com/c8c26675-8b87-4818-ad51-4e0a341965d0">DxgkCbQueueDpc</a> function. This DPC must be queued because the GPU scheduler must also be notified, when the driver's DPC callback routine calls the <a href="https://msdn.microsoft.com/3df3f7d4-3721-46f5-b9e3-19bd3d870292">DxgkCbNotifyDpc</a> function, about the same event at DPC time. A certain amount of processing that is related to graphics hardware events can be only performed by the operating system at DPC time. 

If the display miniport driver determines that more than one interrupt was triggered in hardware and the driver must call <b>DxgkCbNotifyInterrupt</b> for each interrupt to report the interrupt to the operating system, the driver should report DMA-type interrupts before a CRTC-type interrupt. For more information about interrupt types, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561136">DXGK_INTERRUPT_TYPE</a> reference page.

Callers of <b>DxgkCbNotifyInterrupt</b> run at interrupt level (that is, DIRQL, which is some IRQL between DISPATCH_LEVEL and PROFILE_LEVEL, not inclusive).


#### Examples

The following code example shows software engine code that monitors a software queue and notifies the GPU scheduler about packet completion.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _SubmitParams {
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

    DxgkCbNotifyInterrupt = (DXGKCB_NOTIFY_INTERRUPT)pSchNotifyParams-&gt;pHwDeviceExtension-&gt;pVidSchINTCB;

    if(!DxgkCbNotifyInterrupt) {
        return FALSE;
    }

    if(pSchNotifyParams-&gt;PreemptionFenceID) {
        notifyInt.InterruptType = DXGK_INTERRUPT_DMA_PREEMPTED;
        notifyInt.DmaPreempted.PreemptionFenceId = pSchNotifyParams-&gt;PreemptionFenceID;
        notifyInt.DmaPreempted.LastCompletedFenceId = pSchNotifyParams-&gt;FenceID;
        notifyInt.DmaPreempted.NodeOrdinal = pSchNotifyParams-&gt;NodeOrdinal;
    }
    else {
        notifyInt.InterruptType = DXGK_INTERRUPT_DMA_COMPLETED;
        notifyInt.DmaCompleted.SubmissionFenceId = pSchNotifyParams-&gt;FenceID;
        notifyInt.DmaCompleted.NodeOrdinal = pSchNotifyParams-&gt;NodeOrdinal;
    }

    DxgkCbNotifyInterrupt(pSchNotifyParams-&gt;pHwDeviceExtension-&gt;DeviceHandle, &amp;notifyInt);

    pSchNotifyParams-&gt;pHwDeviceExtension-&gt;PrevSubmitFenceIDArray[pSchNotifyParams-&gt;NodeOrdinal] = pSchNotifyParams-&gt;FenceID;

    if(pSchNotifyParams-&gt;PreemptionFenceID) {
        pSchNotifyParams-&gt;pHwDeviceExtension-&gt;PrevPreemptFenceIDArray[pSchNotifyParams-&gt;NodeOrdinal] = pSchNotifyParams-&gt;PreemptionFenceID;
    }

    return TRUE;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557538">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561136">DXGK_INTERRUPT_TYPE</a>



<a href="https://msdn.microsoft.com/3df3f7d4-3721-46f5-b9e3-19bd3d870292">DxgkCbNotifyDpc</a>



<a href="https://msdn.microsoft.com/c8c26675-8b87-4818-ad51-4e0a341965d0">DxgkCbQueueDpc</a>



<a href="https://msdn.microsoft.com/eacfd42d-405c-4c23-8978-0f373a393e10">DxgkDdiInterruptRoutine</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>
 

 

