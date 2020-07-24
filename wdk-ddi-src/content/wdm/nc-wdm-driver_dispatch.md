---
UID: NC:wdm.DRIVER_DISPATCH
title: DRIVER_DISPATCH (wdm.h)
description: The callback routine services various IRPs. For a list of function codes, see Remarks.
old-location: kernel\dispatchcleanup.htm
tech.root: kernel
ms.assetid: 86634953-9c1b-49e6-be44-edb9be911148
ms.date: 04/30/2018
keywords: ["DRIVER_DISPATCH callback function"]
ms.keywords: DRIVER_DISPATCH, DispatchCleanup, DispatchClose, DispatchCreate, DispatchCreateClose, DispatchDeviceControl, DispatchFlushBuffers, DispatchInternalDeviceControl, DispatchPnP, DispatchPower, DispatchQueryInformation, DispatchRead, DispatchReadWrite, DispatchSetInformation, DispatchShutdown, DispatchSystemControl, DispatchWrite, DrvrRtns_157dfedc-63c2-4924-ad5c-04ff9f746a94.xml, MyDispatch, MyDispatch routine [Kernel-Mode Driver Architecture], kernel.dispatchcleanup, wdm/MyDispatch
f1_keywords:
 - "wdm/MyDispatch"
 - "MyDispatch"
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
req.irql: Called at PASSIVE_LEVEL (see Remarks section).
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- MyDispatch
targetos: Windows
req.typenames: 
---

# DRIVER_DISPATCH callback function


## -description


The callback routine services various IRPs. For a list of function codes, see Remarks. 


## -parameters




### -param DeviceObject [in, out]

Caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. This is the device object for the target device, previously created by the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.


### -param Irp [in, out]

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure that describes the requested I/O operation.


## -returns



If the routine succeeds, it must return STATUS_SUCCESS. Otherwise, it must return one of the error status values defined in Ntstatus.h.




## -remarks



Input parameters for all <i>Dispatch</i> routines are supplied in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a> structure pointed to by <i>Irp</i>. Additional parameters are supplied in the driver's associated I/O stack location, which is described by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure and can be obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcurrentirpstacklocation">IoGetCurrentIrpStackLocation</a>.

Generally, all <i>Dispatch</i> routines execute in an arbitrary thread context at IRQL = PASSIVE_LEVEL, but there are exceptions. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/dispatch-routines-and-irqls">Dispatch Routines and IRQLs</a>.

For more information about dispatch routines, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/writing-dispatch-routines">Writing Dispatch Routines</a>. For more information about IRPs, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-irps">Handling IRPs</a>.

<table>
<tr>
<th>IRP</th>
<th>About implementing the callback</th>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup">IRP_MJ_CLEANUP</a>
</td>
<td>
A driver's <i>DispatchCleanup</i> routine should be named <i>Xxx</i>DispatchCleanup, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchCleanup</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_CLEANUP].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>
</td>
<td>
A driver's <i>DispatchClose</i> routine should be named <b><i>Xxx</i>DispatchClose</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchClose</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_CLOSE].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a>
</td>
<td>
A driver's <i>DispatchCreate</i> routine should be named <i>Xxx</i>DispatchCreate, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchCreate</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_CREATE].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-create">IRP_MJ_CREATE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a>
</td>
<td>
A driver can provide a single <i>DispatchCreateClose</i> routine instead of separate <a href="https://msdn.microsoft.com/library/windows/hardware/ff543266">DispatchCreate</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchClose</a> routines.

A driver's <i>DispatchCreateClose</i> routine should be named <b><i>Xxx</i>DispatchCreateClose</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchCreateClose</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_CREATE] and in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_CLOSE].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>
</td>
<td>
A driver's <i>DispatchDeviceControl</i> routine should be named <b><i>Xxx</i>DispatchDeviceControl</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchDeviceControl</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_DEVICE_CONTROL].

The system uses the FILE_<i>XXX</i> flags in the I/O control code to determine whether the IRP sender has the privileges to send the IRP to the device object. Drivers for Windows Server 2003 and later versions of Windows can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iovalidatedeviceiocontrolaccess">IoValidateDeviceIoControlAccess</a> routine to perform stricter access checks within <i>DispatchDeviceControl</i>.

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-flush-buffers">IRP_MJ_FLUSH_BUFFERS</a>
</td>
<td>
A driver's <i>DispatchFlushBuffers</i> routine should be named <i>Xxx</i>DispatchFlushBuffers, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchFlushBuffers</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_FLUSH_BUFFERS].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>
</td>
<td>
A driver's <i>DispatchInternalDeviceControl</i> routine should be named <b><i>Xxx</i>DispatchInternalDeviceControl</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchInternalDeviceControl</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[<b>IRP_MJ_INTERNAL_DEVICE_CONTROL</b>].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-pnp">IRP_MJ_PNP</a>
</td>
<td>
A driver's <i>DispatchPnP</i> routine should be named <i>Xxx</i>DispatchPnP, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchPnP</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_PNP].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-power">IRP_MJ_POWER</a>
</td>
<td>
A driver's <i>DispatchPower</i> routine should be named <b><i>Xxx</i>DispatchPower</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchPower</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[<b>IRP_MJ_POWER</b>].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-information">IRP_MJ_QUERY_INFORMATION</a>
</td>
<td>
A driver's <i>DispatchQueryInformation</i> routine should be named <b><i>Xxx</i>DispatchQueryInformation</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchQueryInformation</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_QUERY_INFORMATION].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>
</td>
<td>
A driver's <i>DispatchRead</i> routine should be named <b><i>Xxx</i>DispatchRead</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchRead</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_READ].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>
</td>
<td>
A driver can provide a single <i>DispatchReadWrite</i> routine instead of separate <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchRead</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_dispatch">DispatchWrite</a> routines.

A driver's <i>DispatchReadWrite</i> routine should be named <b><i>Xxx</i>DispatchReadWrite</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchReadWrite</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[<b>IRP_MJ_READ</b>] and in <i>DriverObject</i>-><b>MajorFunction</b>[<b>IRP_MJ_WRITE</b>].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-information">IRP_MJ_SET_INFORMATION</a>
</td>
<td>
A driver's <i>DispatchSetInformation</i> routine should be named <b><i>Xxx</i>DispatchSetInformation</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchSetInformation</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_SET_INFORMATION].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-shutdown">IRP_MJ_SHUTDOWN</a>
</td>
<td>
A driver's <i>DispatchShutdown</i> routine should be named <b><i>Xxx</i>DispatchShutdown</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchShutdown</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_SHUTDOWN].

Additionally, in order to receive <b>IRP_MJ_SHUTDOWN</b> requests, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregistershutdownnotification">IoRegisterShutdownNotification</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterlastchanceshutdownnotification">IoRegisterLastChanceShutdownNotification</a> to register its <i>DispatchShutdown</i> routine with the system.

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-system-control">IRP_MJ_SYSTEM_CONTROL</a>
</td>
<td>
A driver's <i>DispatchSystemControl</i> routine should be named <b><i>Xxx</i>DispatchSystemControl</b>, where <b><i>Xxx</i></b> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchSystemControl</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_SYSTEM_CONTROL].

</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>
</td>
<td>
A driver's <i>DispatchWrite</i> routine should be named <b><i>Xxx</i>DispatchWrite</b>, where <i>Xxx</i> is a driver-specific prefix. The driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine must store the <i>DispatchWrite</i> routine's address in <i>DriverObject</i>-><b>MajorFunction</b>[IRP_MJ_WRITE].

</td>
</tr>
</table>
 


#### Examples

To define a callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>DispatchCleanup</i> callback routine that is named <code>MyDispatchCleanup</code>, use the DRIVER_DISPATCH type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DRIVER_DISPATCH MyDispatchCleanup;</pre>
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
NTSTATUS
  MyDispatchCleanup(
    struct _DEVICE_OBJECT  *DeviceObject,
    struct _IRP  *Irp
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The DRIVER_DISPATCH function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the DRIVER_DISPATCH function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-using-function-role-types-for-wdm-drivers">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>


