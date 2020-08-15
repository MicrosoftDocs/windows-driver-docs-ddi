---
UID: NC:wdfinterrupt.EVT_WDF_INTERRUPT_SYNCHRONIZE
title: EVT_WDF_INTERRUPT_SYNCHRONIZE (wdfinterrupt.h)
description: A driver's EvtInterruptSynchronize event callback function performs operations that must be synchronized with an EvtInterruptIsr callback function.
old-location: wdf\evtinterruptsynchronize.htm
tech.root: wdf
ms.assetid: ac73b23d-7742-43a4-8950-b301bd0ba330
ms.date: 02/26/2018
keywords: ["EVT_WDF_INTERRUPT_SYNCHRONIZE callback function"]
ms.keywords: DFInterruptObjectRef_4310d770-645e-48c8-bd33-b9edcc8cb667.xml, EVT_WDF_INTERRUPT_SYNCHRONIZE, EVT_WDF_INTERRUPT_SYNCHRONIZE callback, EvtInterruptSynchronize, EvtInterruptSynchronize callback function, kmdf.evtinterruptsynchronize, wdf.evtinterruptsynchronize, wdfinterrupt/EvtInterruptSynchronize
f1_keywords:
 - "wdfinterrupt/EvtInterruptSynchronize"
 - "EvtInterruptSynchronize"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfinterrupt.h
api_name:
- EvtInterruptSynchronize
targetos: Windows
req.typenames: 
---

# EVT_WDF_INTERRUPT_SYNCHRONIZE callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtInterruptSynchronize</i> event callback function performs operations that must be synchronized with an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function.


## -parameters




### -param Interrupt 
[in]
A handle to a framework interrupt object.


### -param Context 
[in]
Driver-supplied information that the driver specifies when it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsynchronize">WdfInterruptSynchronize</a>.


## -returns



The <i>EvtInterruptSynchronize</i> callback function must return <b>TRUE</b> if the operation succeeds. Otherwise, this function must return <b>FALSE</b>. 




## -remarks



To execute an <i>EvtInterruptSynchronize</i> callback function, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsynchronize">WdfInterruptSynchronize</a>. 

If the driver has configured the interrupt object for handling at the device's IRQL (DIRQL), then before calling the <i>EvtInterruptSynchronize</i> callback function, the framework raises the processor's interrupt request level to DIRQL and acquires the spin lock that the driver specified in the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure. 

As a result, while an <i>EvtInterruptSynchronize</i> callback function is executing, the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function (and any other code that executes at DIRQL while holding the spin lock) cannot execute. 

<i>EvtInterruptSynchronize</i> callback functions must be designed so that they execute for only a short period of time. They are typically used to access interrupt data that is also accessed by an interrupt object's other <i>EvtInterruptSynchronize</i> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback functions. 

Beginning with version 1.11 of KMDF, your driver can provide <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-passive-level-interrupts">passive-level interrupt handling</a>. If the driver has requested passive-level interrupt handling, then before calling the <i>EvtInterruptSynchronize</i> function at IRQL = PASSIVE_LEVEL, the framework acquires the passive-level interrupt lock that the driver configured in the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure.

For more information about the <i>EvtInterruptSynchronize</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronizing-interrupt-code">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/ns-wdfinterrupt-_wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinterrupt/nf-wdfinterrupt-wdfinterruptsynchronize">WdfInterruptSynchronize</a>
 

 

