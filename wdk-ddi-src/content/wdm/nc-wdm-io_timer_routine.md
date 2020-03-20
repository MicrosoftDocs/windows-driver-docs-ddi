---
UID: NC:wdm.IO_TIMER_ROUTINE
title: IO_TIMER_ROUTINE (wdm.h)
description: The IoTimer routine is a DPC that, if registered, is called once per second.
old-location: kernel\iotimer.htm
tech.root: kernel
ms.assetid: c41b7489-afd2-4ddf-b296-6d42e3ff6cbf
ms.date: 04/30/2018
keywords: ["IO_TIMER_ROUTINE callback function"]
ms.keywords: DrvrRtns_e0e54c40-37d6-41b3-8374-b1a7763d54ed.xml, IO_TIMER_ROUTINE, IoTimer, IoTimer routine [Kernel-Mode Driver Architecture], kernel.iotimer, wdm/IoTimer
f1_keywords:
 - "wdm/IoTimer"
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
req.irql: Called at DISPATCH_LEVEL (see Remarks section).
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- IoTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IO_TIMER_ROUTINE callback function


## -description


The <i>IoTimer</i> routine is a DPC that, if registered, is called once per second.


## -parameters




### -param *DeviceObject [in]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.


### -param Context [in, optional]

Caller-supplied pointer to driver-defined context information, specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializetimer">IoInitializeTimer</a>.


## -remarks



A driver's <i>IoTimer</i> routine executes in a DPC context, at IRQL = DISPATCH_LEVEL.

A driver can associate an <i>IoTimer</i> routine with each device object it creates. (You can use a single <i>IoTimer</i> routine with multiple device objects, or a separate routine with each device object.) To register an <i>IoTimer</i> routine, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinitializetimer">IoInitializeTimer</a>, supplying the <i>IoTimer</i> routine's address and a device object pointer.

To queue an <i>IoTimer</i> routine for execution, a driver routine must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostarttimer">IoStartTimer</a>. The system calls the <i>IoTimer</i> routine once per second until the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iostoptimer">IoStopTimer</a>.

For more information about <i>IoTimer</i> routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/iotimer-routines">IoTimer Routines</a>.


#### Examples

To define an <i>IoTimer</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define an <i>IoTimer</i> callback routine that is named <code>MyIoTimer</code>, use the IO_TIMER_ROUTINE type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_TIMER_ROUTINE MyIoTimer;</pre>
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
VOID
  MyIoTimer(
    struct DEVICE_OBJECT  *DeviceObject,
    PVOID  Context
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The IO_TIMER_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the IO_TIMER_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>


