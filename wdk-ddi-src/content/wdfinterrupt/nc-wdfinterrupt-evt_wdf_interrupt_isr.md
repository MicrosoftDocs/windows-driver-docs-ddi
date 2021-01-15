---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_ISR
title: EVT_WDF_INTERRUPT_ISR (wdfinterrupt.h)
description: A driver's EvtInterruptIsr event callback function services a hardware interrupt.
old-location: wdf\evtinterruptisr.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_INTERRUPT_ISR callback function"]
ms.keywords: DFInterruptObjectRef_0a8902c4-d292-418f-bab3-d7fc36d69fd5.xml, EVT_WDF_INTERRUPT_ISR, EVT_WDF_INTERRUPT_ISR callback, EvtInterruptIsr, EvtInterruptIsr callback function, kmdf.evtinterruptisr, wdf.evtinterruptisr, wdfinterrupt/EvtInterruptIsr
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
 - EVT_WDF_INTERRUPT_ISR
 - wdfinterrupt/EVT_WDF_INTERRUPT_ISR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfinterrupt.h
api_name:
 - EVT_WDF_INTERRUPT_ISR
---

# EVT_WDF_INTERRUPT_ISR callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtInterruptIsr</i> event callback function services a hardware interrupt.

## -parameters

### -param Interrupt 

[in]
A handle to a framework interrupt object.

### -param MessageID 

[in]
If the device is using message-signaled interrupts (MSIs), this parameter is the message number that identifies the device's hardware interrupt message. Otherwise, this value is 0.

## -returns

The <i>EvtInterruptIsr</i> callback function must return <b>TRUE</b> if the function services the hardware interrupt. Otherwise, this function must return <b>FALSE</b>.

## -remarks

To register an <i>EvtInterruptIsr</i> callback function, your driver must place the callback function's address in a <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>.

The <i>EvtInterruptIsr</i> callback function is a framework-based driver's interrupt service routine (ISR), which is called when a hardware interrupt occurs.

If the interrupt is not from the hardware that this <i>EvtInterruptIsr</i> callback function services, the driver must return <b>FALSE</b>. If the interrupt vector is being shared, the system calls another interrupt service routine.

If the driver has not requested passive-level handling for an interrupt object, then before calling the <i>EvtInterruptIsr</i> callback function, the framework  raises the processor's IRQL to the device's IRQL (DIRQL) and acquires the spin lock that the driver specified in the interrupt object's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure. 

Because the <i>EvtInterruptIsr</i> callback function executes at a relatively high IRQL, it can call very few framework object methods or system routines. Additionally, this callback function cannot access <a href="/windows-hardware/drivers/kernel/making-drivers-pageable">pageable</a> code. 

Typically, the <i>EvtInterruptIsr</i> callback function clears the hardware interrupt and saves any information that might be lost after the callback function returns and the system lowers the IRQL (because lowering the IRQL allows additional interrupts to occur). Framework-based drivers save information about the interrupt in the interrupt object's <a href="/windows-hardware/drivers/wdf/framework-object-context-space">context space</a>. 

Drivers typically provide an <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function  to process the saved information at a lower IRQL. (A few drivers provide one or more <a href="/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a> callback functions instead of an <i>EvtInterruptDpc</i> callback function.) For information about scheduling an <i>EvtInterruptDpc</i> callback function for execution, see <a href="/windows-hardware/drivers/wdf/servicing-an-interrupt">Servicing an Interrupt</a>.

The <i>EvtInterruptIsr</i> callback function must be able to service several interrupts before the <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function executes. Therefore, the driver might have to store interrupt data from several interrupts, and the <i>EvtInterruptIsr</i> and<i>EvtInterruptDpc</i> callback functions might have to determine which interrupt data has been completely processed by the driver and which has not. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level handling for an interrupt object, then before calling that interrupt's <i>EvtInterruptIsr</i> callback function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure. As with interrupt handling at DIRQL, the driver's <i>EvtInterruptIsr</i> function should still save information about the interrupt for later processing.

Drivers that support passive-level interrupt handling can provide either an <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_workitem">EvtInterruptWorkItem</a> or an <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function to process the saved information.

For more information about handling interrupts in framework-based drivers, see <a href="/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdpc/nc-wdfdpc-evt_wdf_dpc">EvtDpcFunc</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptgetdevice">WdfInterruptGetDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptgetinfo">WdfInterruptGetInfo</a>



<a href="/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptwdmgetinterrupt">WdfInterruptWdmGetInterrupt</a>

