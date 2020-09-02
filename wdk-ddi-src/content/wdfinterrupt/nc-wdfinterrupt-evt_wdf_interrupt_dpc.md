---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_DPC
title: EVT_WDF_INTERRUPT_DPC (wdfinterrupt.h)
description: A driver's EvtInterruptDpc event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored.
old-location: wdf\evtinterruptdpc.htm
tech.root: wdf
ms.assetid: d2d505e0-aeac-4871-8c60-d026b2833043
ms.date: 02/26/2018
keywords: ["EVT_WDF_INTERRUPT_DPC callback function"]
ms.keywords: DFInterruptObjectRef_9d7e9cb2-6cfd-4b39-82c8-8a29033e390a.xml, EVT_WDF_INTERRUPT_DPC, EVT_WDF_INTERRUPT_DPC callback, EvtInterruptDpc, EvtInterruptDpc callback function, kmdf.evtinterruptdpc, wdf.evtinterruptdpc, wdfinterrupt/EvtInterruptDpc
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_INTERRUPT_DPC
 - wdfinterrupt/EVT_WDF_INTERRUPT_DPC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfinterrupt.h
api_name:
 - EvtInterruptDpc
---

# EVT_WDF_INTERRUPT_DPC callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtInterruptDpc</i> event callback function processes interrupt information that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function has stored.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

### -param AssociatedObject 

[in]
A handle to the framework device object that the driver passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

## -remarks

To register an <i>EvtInterruptDpc</i> callback function, your driver must place the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

Drivers typically <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">complete I/O requests</a> in their <i>EvtInterruptDpc</i> callback functions.

The <i>EvtInterruptDpc</i> callback function executes at DISPATCH_LEVEL and must not access <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/making-drivers-pageable">pageable</a> code. If an <i>EvtInterruptDpc</i> callback function must perform operations at IRQL = PASSIVE_LEVEL, it can <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-work-items">use framework work items</a>. 

In KMDF version 1.11 and later, your driver can support <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupts</a> and provide either an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> or an <i>EvtInterruptDpc</i> callback function. If your driver supports passive-level interrupts and provides an <i>EvtInterruptDpc</i> callback function, the driver cannot acquire the passive-level interrupt lock from within the callback.

Most drivers use a single <i>EvtInterruptDpc</i> callback function for each type of interrupt. If your driver creates multiple <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-queue-objects">framework queue objects</a> for each device, you might consider using a separate <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/">DPC object</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback function for each queue.

To schedule execution of an <i>EvtInterruptDpc</i> callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptqueuedpcforisr">WdfInterruptQueueDpcForIsr</a> from within the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function.

When a driver schedules the execution of an <i>EvtInterruptDpc</i> callback function, the system adds a DPC object to the system's DPC queue. If the system is not executing higher-priority tasks, it removes the object from the queue and calls the <i>EvtInterruptDpc</i> callback function. 

The system does not add the DPC object to the DPC queue if the object is already queued. An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function might be called several times before the system calls the <i>EvtInterruptDpc</i> callback function. Therefore, the <i>EvtInterruptDpc</i> callback function must be able to process information from several interrupts, and it must process all interrupts that have occurred since the last time it was called.

Typically, it is necessary to synchronize the execution of a driver's <i>EvtInterruptDpc</i> callback function with the execution of other callback functions. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronizing-interrupt-code">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptqueuedpcforisr">WdfInterruptQueueDpcForIsr</a>

