---
UID: NC:wdm.IO_DPC_ROUTINE
title: IO_DPC_ROUTINE (wdm.h)
description: The DpcForIsr routine finishes the servicing of an I/O operation, after an InterruptService routine returns.
old-location: kernel\dpcforisr.htm
tech.root: kernel
ms.assetid: 834b1ad0-82e4-481d-93cc-1f46c20fcba3
ms.date: 04/30/2018
keywords: ["IO_DPC_ROUTINE callback function"]
ms.keywords: DpcForIsr, DpcForIsr routine [Kernel-Mode Driver Architecture], DrvrRtns_2d3825cf-0f9b-4698-9deb-e9fe5757fb9c.xml, IO_DPC_ROUTINE, kernel.dpcforisr, wdm/DpcForIsr
f1_keywords:
 - "wdm/DpcForIsr"
 - "DpcForIsr"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: Called at DISPATCH_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- DpcForIsr
targetos: Windows
req.typenames: 
---

# IO_DPC_ROUTINE callback function


## -description


The <i>DpcForIsr</i> routine finishes the servicing of an I/O operation, after an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> routine returns.


## -parameters




### -param Dpc [in]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">KDPC</a> structure, which represents the DPC object that is associated with this <i>DpcForIsr</i> routine. 


### -param DeviceObject [in]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.


### -param Irp [in, out]

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure that describes the I/O operation.


### -param Context [in, optional]

Caller-supplied pointer to driver-defined context information, specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc">IoRequestDpc</a>.


## -remarks



To register a <i>DpcForIsr</i> routine for a specific device object, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializedpcrequest">IoInitializeDpcRequest</a>, which causes the system to allocate and initialize one DPC object. (If you need multiple DPC routines, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kdeferred_routine">CustomDpc</a> routines.)

To queue a <i>DpcForIsr</i> routine for execution, a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> routine must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iorequestdpc">IoRequestDPC</a>.

A <i>DpcForIsr</i> routine is typically responsible for at least the following tasks:

<ul>
<li>
Completing the I/O operation described by the received IRP. 

</li>
<li>
Dequeuing next IRP.

If the driver uses the system-supplied IRP queue, the <i>DpcForIsr</i> routine should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartnextpacket">IoStartNextPacket</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostartnextpacketbykey">IoStartNextPacketByKey</a>, so the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_startio">StartIo</a> routine will start processing the next I/O request.

If the driver uses internal IRP queues, the <i>DpcForIsr</i> routine should dequeue the next IRP and begin processing for the next I/O request. 

</li>
<li>
Setting the I/O status block in the received IRP and calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a> for the completed request.

</li>
</ul>
A <i>DpcForIsr</i> routine might also retry a failed operation or set up the next transfer for a large I/O request that has been broken into smaller pieces.

For more information about <i>DpcForIsr</i> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/dpc-objects-and-dpcs">DPC Objects and DPCs</a>. 


#### Examples

To define a <i>DpcForIsr</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>DpcForIsr</i> callback routine that is named <code>MyDpcForIsr</code>, use the IO_DPC_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_DPC_ROUTINE MyDpcForIsr;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
_Use_decl_annotations_
VOID
  MyDpcForIsr(
    PKDPC  Dpc,
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp,
    PVOID  Context
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_DPC_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_DPC_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>


