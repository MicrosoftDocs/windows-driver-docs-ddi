---
UID: NF:wdfinterrupt.WdfInterruptQueueDpcForIsr
title: WdfInterruptQueueDpcForIsr function (wdfinterrupt.h)
description: The WdfInterruptQueueDpcForIsr method queues a framework interrupt object's EvtInterruptDpc callback function for execution.
old-location: wdf\wdfinterruptqueuedpcforisr.htm
tech.root: wdf
ms.assetid: ba9a292d-12c8-41b5-bddb-7c8ebf4fdc48
ms.date: 02/26/2018
ms.keywords: DFInterruptObjectRef_c77c2aa3-e142-4226-aa9d-fb31d408e335.xml, WdfInterruptQueueDpcForIsr, WdfInterruptQueueDpcForIsr method, kmdf.wdfinterruptqueuedpcforisr, wdf.wdfinterruptqueuedpcforisr, wdfinterrupt/WdfInterruptQueueDpcForIsr
ms.topic: function
f1_keywords:
 - "wdfinterrupt/WdfInterruptQueueDpcForIsr"
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
- WdfInterruptQueueDpcForIsr
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfInterruptQueueDpcForIsr function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfInterruptQueueDpcForIsr</b> method queues a framework interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function for execution.


## -parameters




### -param Interrupt [in]

A handle to a framework interrupt object.


## -returns



<b>WdfInterruptQueueDpcForIsr</b> returns <b>TRUE</b> if it successfully queues the interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function. The method returns <b>FALSE</b> if the callback function was previously queued and has not executed.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers typically call <b>WdfInterruptQueueDpcForIsr</b> from within an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function.

An interrupt object's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function can be queued only once before it executes. Therefore, if a call to <b>WdfInterruptQueueDpcForIsr</b> succeeds, subsequent calls will return <b>FALSE</b> until the framework dequeues the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback will run on the processor that enqueued it. If your driver calls <b>WdfInterruptQueueDpcForIsr</b> to queue another DPC while an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function is already dequeued or running, the second <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback might even run before the first one completes.

For more information about handling interrupts in framework-based drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-hardware-interrupts">Handling Hardware Interrupts</a>.

In KMDF 1.11 and later, a driver can call <b>WdfInterruptQueueDpcForIsr</b> from a passive-level ISR.  Note that a driver can register a work item or a DPC but not both.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a> callback function should queue an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
MyEvtInterruptIsr(
    IN WDFINTERRUPT Interrupt,
    IN ULONG  MessageID
    )
{
    BOOLEAN queueDpcSuccess;

    //
    // Save interrupt information for the
    // EvtInterruptDpc function.
    //
...
    //
    // Queue the EvtInterruptDpc function.
    //
    queueDpcSuccess = WdfInterruptQueueDpcForIsr(Interrupt);
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_isr">EvtInterruptIsr</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfinterrupt/nf-wdfinterrupt-wdfinterruptcreate">WdfInterruptCreate</a>
 

 

