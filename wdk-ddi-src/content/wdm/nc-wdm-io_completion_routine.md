---
UID: NC:wdm.IO_COMPLETION_ROUTINE
title: IO_COMPLETION_ROUTINE (wdm.h)
description: The IoCompletion routine completes the processing of I/O operations.
old-location: kernel\iocompletion.htm
tech.root: kernel
ms.assetid: 53fc5265-5d8e-4794-942b-de81b93e81da
ms.date: 04/30/2018
keywords: ["IO_COMPLETION_ROUTINE callback function"]
ms.keywords: DrvrRtns_aa2b6363-e3c1-4243-87d8-8a1bb575974b.xml, IO_COMPLETION_ROUTINE, IoCompletion, IoCompletion routine [Kernel-Mode Driver Architecture], kernel.iocompletion, wdm/IoCompletion
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
req.irql: Called at IRQL <= DISPATCH_LEVEL (see Remarks section).
targetos: Windows
req.typenames: 
f1_keywords:
 - IO_COMPLETION_ROUTINE
 - wdm/IO_COMPLETION_ROUTINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - IoCompletion
---

# IO_COMPLETION_ROUTINE callback function


## -description

The <i>IoCompletion</i> routine completes the processing of I/O operations.

## -parameters

### -param DeviceObject 

[in]
Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.

### -param Irp 

[in]
Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure that describes the I/O operation.

### -param Context 

[in, optional]
Caller-supplied pointer to driver-specific context information, previously supplied when calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutineex">IoSetCompletionRoutineEx</a>. Context information must be stored in nonpaged memory, since an <i>IoCompletion</i> routine can be called at DISPATCH_LEVEL. For more information, see the following Remarks section.

## -returns

If the <i>IoCompletion</i> routine determines that additional processing is required for the IRP, it must return STATUS_MORE_PROCESSING_REQUIRED. For more information, see the following Remarks section. Otherwise, it should return STATUS_SUCCESS. (The I/O manager only checks for the presence or absence of STATUS_MORE_PROCESSING_REQUIRED.)

## -remarks

A driver's <i>IoCompletion</i> routine executes in an arbitrary thread or DPC context, and at an IRQL that is less than or equal to DISPATCH_LEVEL. Because code written to execute at DISPATCH_LEVEL will also execute at lower levels, <i>IoCompletion</i> routines should be designed for execution at DISPATCH_LEVEL. However, because these routines are not guaranteed to run at DISPATCH_LEVEL, they must not call system routines that actually require execution at DISPATCH_LEVEL. (For more information about IRQLs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/managing-hardware-priorities">Managing Hardware Priorities</a>.)

To register an <i>IoCompletion</i> routine for a specific IRP, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutineex">IoSetCompletionRoutineEx</a>, which stores the <i>IoCompletion</i> routine's address in the next-lower driver's I/O stack location. (Thus, a lowest-level driver <u>cannot</u> register an <i>IoCompletion</i> routine.) A driver typically calls <b>IoSetCompletionRoutine</b> or <b>IoSetCompletionRoutineEx</b> from one of its dispatch routines, each time an IRP is received. Most drivers, including all PnP drivers, can use<b> IoSetCompletionRoutine</b> to register their <i>IoCompletion</i> routine. Non-PnP drivers that may be unloaded before their <i>IoCompletion</i> routine executes should use <b>IoSetCompletionRoutineEx</b> instead.

When any driver completes an IRP, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>, which in turn calls the <i>IoCompletion</i> routine of each higher-level driver, from the next-highest to the highest, until all higher <i>IoCompletion</i> routines have been called or until one routine returns STATUS_MORE_PROCESSING_REQUIRED.

When you create the IRP, allocate a stack location for the current driver as well as any lower drivers. If you do not allocate sufficient stack locations, the <i>DeviceObject</i> pointer might be set to <b>NULL</b> when the completion routine is called. You can avoid allocating extra stack location for the current driver if you use the <i>Context</i> field to pass information to <i>IoCompletion</i> rather then relying on the <i>DeviceObject</i> parameter.

If an <i>IoCompletion</i> routine returns STATUS_MORE_PROCESSING_REQUIRED, the lower driver's call to <b>IoCompleteRequest</b> immediately returns. In this case, a higher-level driver will have to call <b>IoCompleteRequest</b> to complete the IRP.

For more information about implementing <i>IoCompletion</i> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/completing-irps">Completing IRPs</a>.


#### Examples

To define an <i>IoCompletion</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>IoCompletion</i> callback routine that is named <code>MyIoCompletion</code>, use the IO_COMPLETION_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_COMPLETION_ROUTINE MyIoCompletion;</pre>
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
<pre>_Use_decl_annotations_
NTSTATUS
  MyIoCompletion(
    PDEVICE_OBJECT  DeviceObject,
    PIRP  Irp,
    PVOID  Context
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_COMPLETION_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_COMPLETION_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>

