---
UID: NC:wdm.DRIVER_STARTIO
title: DRIVER_STARTIO (wdm.h)
description: The StartIo routine starts the I/O operation described by an IRP.
old-location: kernel\startio.htm
tech.root: kernel
ms.assetid: 86ec9f67-346d-4ace-8bf0-a15dd57f0a89
ms.date: 04/30/2018
ms.keywords: DRIVER_STARTIO, DrvrRtns_3227d9e5-10b6-449f-af47-48574e7a00d5.xml, StartIo, StartIo routine [Kernel-Mode Driver Architecture], kernel.startio, wdm/StartIo
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	StartIo
product:
- Windows
targetos: Windows
req.typenames: 
---

# DRIVER_STARTIO callback function


## -description


The <i>StartIo</i> routine starts the I/O operation described by an IRP.


## -parameters




### -param *DeviceObject [in, out]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine.


### -param *Irp [in, out]

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure that describes the requested I/O operation.


## -returns



None




## -remarks



A driver's <i>StartIo</i> routine executes in an arbitrary thread context at IRQL = DISPATCH_LEVEL.

The <i>StartIo</i> routine is optional. A driver's <i>StartIo</i> routine, if supplied, should be named <i>Xxx</i><b>StartIo</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine must store the <i>StartIo</i> routine's address in <b>DriverObject-&gt;DriverStartIo</b>. (If no routine is supplied, this pointer must be <b>NULL</b>.)

A driver can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550330">IoSetStartIoAttributes</a> to set attributes on when its <i>StartIo</i> routine is called.

For detailed information about implementing a driver's <i>StartIo</i> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566404">Writing a StartIo Routine</a>.


#### Examples

To define a <i>StartIo</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>StartIo</i> callback routine that is named <code>MyStartIo</code>, use the DRIVER_STARTIO type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DRIVER_STARTIO MyStartIo;</pre>
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
  MyStartIo(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp 
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The DRIVER_STARTIO function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_STARTIO function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>


