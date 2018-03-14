---
UID: NC:d3dkmddi.DXGKCB_NOTIFY_INTERRUPT
title: DXGKCB_NOTIFY_INTERRUPT
author: windows-driver-content
description: The DxgkCbNotifyInterrupt function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at interrupt-service-routine (ISR) time.
old-location: display\dxgkcbnotifyinterrupt.htm
old-project: display
ms.assetid: 7968d26d-0195-463d-8954-e7ebef4f9dea
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKCB_NOTIFY_INTERRUPT, DpFunctions_fdb60c96-9eec-4e57-a4bd-1b97ad99769b.xml, DxgkCbNotifyInterrupt, DxgkCbNotifyInterrupt callback function [Display Devices], d3dkmddi/DxgkCbNotifyInterrupt, display.dxgkcbnotifyinterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_NOTIFY_INTERRUPT callback


## -description


The <b>DxgkCbNotifyInterrupt</b> function informs the graphics processing unit (GPU) scheduler about a graphics hardware update at interrupt-service-routine (ISR) time.


## -prototype


````
DXGKCB_NOTIFY_INTERRUPT DxgkCbNotifyInterrupt;

VOID APIENTRY DxgkCbNotifyInterrupt(
  _In_    const HANDLE                          hAdapter,
  _Inout_ const DXGKARGCB_NOTIFY_INTERRUPT_DATA *pData
)
{ ... }
````


## -parameters




### -param hAdapter [in]

[in] A handle to the adapter object for the GPU. A driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure in a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


#### - pData [in, out]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure that describes notification information.


## -returns



None




## -remarks



A display miniport driver calls the <b>DxgkCbNotifyInterrupt</b> function to report a graphics hardware interrupt that the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a> enumeration type defines. Typically, <b>DxgkCbNotifyInterrupt</b> is called from the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function (ISR), which is called when graphics hardware interrupts occur. The <b>DxgkCbNotifyInterrupt</b> function informs the GPU scheduler about an update to a fence through a direct memory access (DMA) stream to the graphics hardware. 

If the display miniport driver uses multiple interrupt handlers that correspond to multiple IRQLs, the driver must not call <b>DxgkCbNotifyInterrupt</b> in a reentrant fashion. Therefore, in this case, the display miniport driver should always call <b>DxgkCbNotifyInterrupt</b> from a fixed level of the interrupt handler. 

Similarly, if message-signaled interrupts are used, the display miniport driver can call <b>DxgkCbNotifyInterrupt</b> from an interrupt handler that corresponds to a fixed message number. The driver must report the message number that is used for notification in the <b>InterruptMessageNumber</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a> structure, when the DXGKQAITYPE_DRIVERCAPS enumeration value is specified in the <b>Type</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a> structure in a call to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.

After the display miniport driver calls <b>DxgkCbNotifyInterrupt</b> but before the driver exits its ISR, the driver must queue a deferred procedure call (DPC) by using the <a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a> function. This DPC must be queued because the GPU scheduler must also be notified, when the driver's DPC callback routine calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a> function, about the same event at DPC time. A certain amount of processing that is related to graphics hardware events can be only performed by the operating system at DPC time. 

If the display miniport driver determines that more than one interrupt was triggered in hardware and the driver must call <b>DxgkCbNotifyInterrupt</b> for each interrupt to report the interrupt to the operating system, the driver should report DMA-type interrupts before a CRTC-type interrupt. For more information about interrupt types, see the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a> reference page.

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

<a href="..\dispmprt\nc-dispmprt-dxgkcb_queue_dpc.md">DxgkCbQueueDpc</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_NOTIFY_INTERRUPT callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

