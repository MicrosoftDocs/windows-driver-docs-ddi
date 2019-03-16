---
UID: NF:wdm.IoBuildAsynchronousFsdRequest
title: IoBuildAsynchronousFsdRequest function (wdm.h)
description: The IoBuildAsynchronousFsdRequest routine allocates and sets up an IRP to be sent to lower-level drivers.
old-location: kernel\iobuildasynchronousfsdrequest.htm
tech.root: kernel
ms.assetid: cb633146-c3ab-4a09-bbcd-5964ecbf6e44
ms.date: 04/30/2018
ms.keywords: IoBuildAsynchronousFsdRequest, IoBuildAsynchronousFsdRequest routine [Kernel-Mode Driver Architecture], k104_bbefd6f7-02b9-497d-9d9e-aef507436cd4.xml, kernel.iobuildasynchronousfsdrequest, wdm/IoBuildAsynchronousFsdRequest
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: ForwardedAtBadIrqlFsdAsync, IoBuildFsdComplete, IoBuildFsdForward, IoBuildFsdFree, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoBuildAsynchronousFsdRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoBuildAsynchronousFsdRequest function


## -description


The <b>IoBuildAsynchronousFsdRequest</b> routine allocates and sets up an IRP to be sent to lower-level drivers.


## -parameters




### -param MajorFunction [in]

The major function code to be set in the IRP. This code can be <a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549235">IRP_MJ_FLUSH_BUFFERS</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a>.


### -param DeviceObject [in]

A pointer to the next-lower driver's device object. This object represents the target device for the read, write, flush, or shutdown operation.


### -param Buffer [in, out]

A pointer to a buffer into which data is read or from which data is written. The value of this argument is <b>NULL</b> for flush and shutdown requests.


### -param Length [in, optional]

The length, in bytes, of the buffer pointed to by <i>Buffer</i>. For devices such as disks, this value must be an integer multiple of the sector size. Starting with Windows 8, the sector size can be 4,096 or 512 bytes. In earlier versions of Windows, the sector size is always 512 bytes. This parameter is required for read and write requests, but must be zero for flush and shutdown requests.


### -param StartingOffset [in, optional]

A pointer to the starting offset on the input/output media. The value of this argument is zero for flush and shutdown requests.


### -param IoStatusBlock [in, optional]

A pointer to the address of an I/O status block in which the to-be-called drivers return final status about the requested operation.


## -returns



<b>IoBuildAsynchronousFsdRequest</b> returns a pointer to an IRP, or a <b>NULL</b> pointer if the IRP cannot be allocated.




## -remarks



Intermediate or highest-level drivers can call <b>IoBuildAsynchronousFsdRequest</b> to set up IRPs for requests sent to lower-level drivers. The calling driver must supply an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine for the IRP, so the IRP can be deallocated with <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>. For more information about IRP deallocation, see Examples.

The IRP that gets built contains only enough information to get the operation started and to complete the IRP. No other context information is tracked because an asynchronous request is context-independent.

Lower-level drivers might impose restrictions on parameters supplied to this routine. For example, disk drivers might require that values supplied for <i>Length</i> and <i>StartingOffset</i> be integer multiples of the device's sector size.

An intermediate or highest-level driver also can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a> to set up requests it sends to lower-level drivers. Only a highest-level driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>.

During an <b>IoBuildAsynchronousFsdRequest</b> call, the I/O manager sets the <b>Tail.Overlay.Thread</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure to point to the caller's thread object, but does <u>not</u> take a counted reference to the thread object on behalf of the caller. After the caller sends the IRP to the driver for the target device, this driver might use the <b>Tail.Overlay.Thread</b> member to access the thread object. For example, a storage driver might call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549707">IoSetHardErrorOrVerifyDevice</a> routine and supply a pointer to the IRP as an input parameter. During this call, <b>IoSetHardErrorOrVerifyDevice</b> uses the <b>Tail.Overlay.Thread</b> member to access the thread object. When the thread object is accessed in this way, the driver that called <b>IoBuildAsynchronousFsdRequest</b> to allocate the IRP is responsible for ensuring that the thread object stays valid while the IRP is being handled.

To keep the thread object valid, the driver that calls <b>IoBuildAsynchronousFsdRequest</b> can take a counted reference on the thread object before sending the IRP. For example, this driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558688">ObReferenceObjectByPointerWithTag</a> routine and supply, as the <i>Object</i> parameter, the object pointer from the <b>Tail.Overlay.Thread</b> member of the <b>IRP</b> structure. Later, this driver's completion routine can dereference the object by calling a routine such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff557734">ObDereferenceObjectWithTag</a>.

A driver might call <b>IoBuildAsynchronousFsdRequest</b> in one thread, and send the IRP allocated by this call in another thread. Before sending the IRP, this driver should set the <b>Tail.Overlay.Thread</b> member of the IRP to point to the thread object for the sending thread. Typically, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a> routine to get the thread object pointer.

A driver that calls <b>IoBuildAsynchronousFsdRequest</b> to allocate an IRP does not necessarily need to take a counted reference on the thread object pointed to by the <b>Tail.Overlay.Thread</b> member of the IRP. The driver might instead use another technique to guarantee that this thread object remains valid while the IRP is being handled. For example, if the driver created the thread, the thread can wait until the IRP is completed to terminate itself.


#### Examples

Before calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>, an additional step is required to free the buffer for an IRP built by <b>IoBuildAsynchronousFsdRequest</b> if the following are all true:

<ul>
<li>The buffer was allocated from system memory pool.</li>
<li>In the device object for the target device, the DO_DIRECT_IO flag is set in the <b>DeviceObject-&gt;Flags</b> field.</li>
<li>The <b>Irp-&gt;MdlAddress</b> field is non-NULL.</li>
</ul>
Before freeing the buffer for this IRP, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556381">MmUnlockPages</a> routine with <b>Irp-&gt;MdlAddress</b> as the parameter value. This call decrements the extra reference count that <b>IoBuildAsynchronousFsdRequest</b> added to the pool pages in the MDL. Otherwise, the subsequent call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a> will bug check because the reference count for these pool pages will be 2, not 1. The following code example shows the <b>MmUnlockPages</b>, <b>IoFreeMdl</b>, and <b>IoFreeIrp</b> calls for this case:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>if (((DeviceObject-&gt;Flags &amp; DO_DIRECT_IO) == DO_DIRECT_IO) &amp;&amp;
    (Irp-&gt;MdlAddress != NULL))
{
    MmUnlockPages(Irp-&gt;MdlAddress);
}

IoFreeMdl(Irp-&gt;MdlAddress);
IoFreeIrp(Irp);
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548257">IoAllocateIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548336">IoCallDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549126">IoFreeMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549679">IoSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549707">IoSetHardErrorOrVerifyDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556381">MmUnlockPages</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557734">ObDereferenceObjectWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558688">ObReferenceObjectByPointerWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559936">PsGetCurrentThread</a>
 

 

