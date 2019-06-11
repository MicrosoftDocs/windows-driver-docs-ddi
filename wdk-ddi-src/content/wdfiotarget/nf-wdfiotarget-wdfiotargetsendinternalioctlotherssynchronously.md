---
UID: NF:wdfiotarget.WdfIoTargetSendInternalIoctlOthersSynchronously
title: WdfIoTargetSendInternalIoctlOthersSynchronously function (wdfiotarget.h)
description: The WdfIoTargetSendInternalIoctlOthersSynchronously method builds a non-standard internal device control request and sends it synchronously to an I/O target.
old-location: wdf\wdfiotargetsendinternalioctlotherssynchronously.htm
tech.root: wdf
ms.assetid: 53070b37-3836-49c2-91d1-369552afe214
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_78072360-08c2-4a51-be52-8e00425c5ba2.xml, WdfIoTargetSendInternalIoctlOthersSynchronously, WdfIoTargetSendInternalIoctlOthersSynchronously method, kmdf.wdfiotargetsendinternalioctlotherssynchronously, wdf.wdfiotargetsendinternalioctlotherssynchronously, wdfiotarget/WdfIoTargetSendInternalIoctlOthersSynchronously
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, IoctlReqs, KmdfIrql, KmdfIrql2, ReadReqs, RequestCompleted, RequestCompletedLocal, WriteReqs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfIoTargetSendInternalIoctlOthersSynchronously
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetSendInternalIoctlOthersSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method builds a non-standard internal device control request and sends it synchronously to an I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param IoctlCode [in]

An I/O control code (IOCTL) that the I/O target supports. 


### -param OtherArg1 [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a> structure that describes a memory buffer that contains context information. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg2 [in, optional]

A pointer to a WDF_MEMORY_DESCRIPTOR structure that describes a memory buffer that contains context information. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg4 [in, optional]

A pointer to a WDF_MEMORY_DESCRIPTOR structure that describes a memory buffer that contains context information. This parameter is optional and can be <b>NULL</b>.


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param BytesReturned [out, optional]

A pointer to a location that receives information (such as the number of bytes that were transferred) that another driver supplies when it completes the request by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>. This pointer is optional and can be <b>NULL</b>.


## -returns



If the operation succeeds, <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> returns after the internal device control request completes, and the return value is the request's completion status value. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter pointed to was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate system resources (typically memory).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The driver supplied a time-out value and the request did not complete within the allotted time.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>
</td>
<td width="60%">
The I/O request packet (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A non-standard internal device control request uses an IOCTL code to identify the operation to be performed, but the request does not use the standard input and output buffers that other internal device control requests use. If you are creating a set of interacting drivers, you can define how this set of drivers use the request's arguments: <i>OtherArg1</i>, <i>OtherArg2</i>, and <i>OtherArg4</i>. 

There is no parameter called <i>OtherArg3</i> because the framework associates these parameters with the <b>Argument1</b>, <b>Argument2</b>, and <b>Argument4</b> members of the <b>Other.Parameters</b> union in the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure. The <b>Argument3</b> member in that union receives the value from the <i>IoctlCode</i> parameter, so it is  not available for other driver-supplied values.

Use the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method to send non-standard internal device control requests synchronously. To send internal device control requests asynchronously, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff548599">WdfIoTargetFormatRequestForInternalIoctlOthers</a>, followed by <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>. 

For more information about internal device control requests, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.

The <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <i>RequestOptions</i> parameter's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure, or unless an error is detected.

You can forward a non-standard internal device control request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and possibly some context space.

To forward a non-standard internal device control request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>Request</i> parameter.

</li>
<li>
Use the received request's context information for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>OtherArg1</i>,<i>OtherArg2</i>, and<i>OtherArg4</i> parameters.

To obtain these parameter values, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a> and use the <b>DeviceIoControl</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure that is returned. 

</li>
</ol>
For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

<ol>
<li>
Supply a <b>NULL</b> request handle for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>Request</i> parameter, or create a new request object and supply its handle:<ul>
<li>If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.</li>
<li>If you call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. This technique enables your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549941">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.</li>
</ul>


Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

</li>
<li>
Provide context space for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>OtherArg1</i>,<i>OtherArg2</i>, and <i>OtherArg4</i> parameters, if the request requires them.

Your driver can specify this context space as locally allocated buffers, as WDFMEMORY handles, or as memory descriptor lists (MDLs). You can use whichever method is most convenient. 

The following techniques to specify buffer space are available:

<ul>
<li>
Supply local buffers.

Because <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> handles I/O requests synchronously, the driver can create request buffers that are local to the calling routine, as the following code example shows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  MemoryDescriptor;
MY_BUFFER_TYPE  MyBuffer;
WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(&MemoryDescriptor,
                                  (PVOID) &MyBuffer,
                                  sizeof(MyBuffer));</pre>
</td>
</tr>
</table></span></div>
</li>
<li>
Supply WDFMEMORY handles.

Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a> to obtain a handle to framework-managed memory, as the following code example shows. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  MemoryDescriptor;
WDFMEMORY  MemoryHandle = NULL;
status = WdfMemoryCreate(NULL,
                         NonPagedPool,
                         POOL_TAG,
                         MY_BUFFER_SIZE,
                         &MemoryHandle,
                         NULL);
WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(&MemoryDescriptor,
                                  MemoryHandle,
                                  NULL);</pre>
</td>
</tr>
</table></span></div>
</li>
<li>
Supply MDLs.

Drivers can obtain MDLs that are associated with a received I/O request by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550016">WdfRequestRetrieveInputWdmMdl</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550021">WdfRequestRetrieveOutputWdmMdl</a>.

</li>
</ul>
</li>
</ol>
For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b>, see <a href="https://msdn.microsoft.com/3fa897f5-2de8-484b-becb-c2de23fb5e8c">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example initializes an IEEE 1394 IRB structure, uses the structure's address to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a> structure, and then calls <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b>. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR descriptor;
IRB Irb;

Irb.FunctionNumber = REQUEST_ALLOCATE_ADDRESS_RANGE;
Irb.Flags = 0;
Irb.u.AllocateAddressRange.Mdl = pAsyncAddressData->pMdl;
Irb.u.AllocateAddressRange.fulFlags = fulFlags;
Irb.u.AllocateAddressRange.nLength = nLength;
Irb.u.AllocateAddressRange.MaxSegmentSize = MaxSegmentSize;
Irb.u.AllocateAddressRange.fulAccessType = fulAccessType;
Irb.u.AllocateAddressRange.fulNotificationOptions = fulNotificationOptions;
Irb.u.AllocateAddressRange.Callback = NULL;
Irb.u.AllocateAddressRange.Context = NULL;
Irb.u.AllocateAddressRange.Required1394Offset = *Required1394Offset;
Irb.u.AllocateAddressRange.FifoSListHead = NULL;
Irb.u.AllocateAddressRange.FifoSpinLock = NULL;
Irb.u.AllocateAddressRange.AddressesReturned = 0;
Irb.u.AllocateAddressRange.p1394AddressRange = pAsyncAddressData->AddressRange;
Irb.u.AllocateAddressRange.DeviceExtension = deviceExtension;

WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(
                                  &descriptor,
                                  &Irb,
                                  sizeof (IRB)
                                  );

ntStatus = WdfIoTargetSendInternalIoctlOthersSynchronously(
                                                           IoTarget, 
                                                           NULL,
                                                           IOCTL_1394_CLASS,
                                                           &descriptor,
                                                           NULL,
                                                           NULL,
                                                           NULL,
                                                           NULL
                                                           );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552393">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548599">WdfIoTargetFormatRequestForInternalIoctlOthers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549941">WdfRequestCancelSentRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550016">WdfRequestRetrieveInputWdmMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550021">WdfRequestRetrieveOutputWdmMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>
 

 

