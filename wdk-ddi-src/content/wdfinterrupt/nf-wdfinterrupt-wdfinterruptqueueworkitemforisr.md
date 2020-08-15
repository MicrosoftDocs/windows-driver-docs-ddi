---
UID: NF:wdfinterrupt.WdfInterruptQueueWorkItemForIsr
title: WdfInterruptQueueWorkItemForIsr function (wdfinterrupt.h)
description: The WdfInterruptQueueWorkItemForIsr method queues a framework interrupt object's EvtInterruptWorkItem callback function for execution.
old-location: wdf\wdfinterruptqueueworkitemforisr.htm
tech.root: wdf
ms.assetid: 1E88E9D9-B564-43B4-9A83-F621FF23437F
ms.date: 02/26/2018
keywords: ["WdfInterruptQueueWorkItemForIsr function"]
ms.keywords: WdfInterruptQueueWorkItemForIsr, WdfInterruptQueueWorkItemForIsr method, kmdf.wdfinterruptqueueworkitemforisr, wdf.wdfinterruptqueueworkitemforisr, wdfinterrupt/WdfInterruptQueueWorkItemForIsr
f1_keywords:
 - "wdfinterrupt/WdfInterruptQueueWorkItemForIsr"
 - "WdfInterruptQueueWorkItemForIsr"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DIRQL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfInterruptQueueWorkItemForIsr
targetos: Windows
req.typenames: 
---

# WdfInterruptQueueWorkItemForIsr function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptQueueWorkItemForIsr</b> method queues a framework interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> callback function for execution.


## -parameters




### -param Interrupt 
[in]
A handle to a framework interrupt object.


## -returns




      If the driver's ISR is running at IRQL = PASSIVE_LEVEL, <b>WdfInterruptQueueWorkItemForIsr</b> returns <b>TRUE</b> if it successfully queues the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> callback function. The method returns <b>FALSE</b> if the callback function was previously queued and has not executed.


      If the driver's ISR is running at IRQL = DIRQL, the framework first queues an internal DPC and then queues a work item from that DPC. In this case, <b>WdfInterruptQueueWorkItemForIsr</b> returns <b>TRUE</b> if the framework successfully queues the internal DPC. The method returns <b>FALSE</b> if the internal DPC was previously queued.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers typically call <b>WdfInterruptQueueWorkItemForIsr</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function.

An interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> callback function can be queued only once before it executes. Therefore, if a call to <b>WdfInterruptQueueWorkItemForIsr</b> succeeds, subsequent calls will not queue additional callbacks.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

  A bug check occurs if drivers call <b>WdfInterruptQueueWorkItemForIsr</b> with an interrupt object that does not specify an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> callback function.






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptqueuedpcforisr">WdfInterruptQueueDpcForIsr</a>
 

 

