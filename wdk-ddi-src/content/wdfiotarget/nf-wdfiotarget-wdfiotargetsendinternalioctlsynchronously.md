---
UID: NF:wdfiotarget.WdfIoTargetSendInternalIoctlSynchronously
title: WdfIoTargetSendInternalIoctlSynchronously function
author: windows-driver-content
description: The WdfIoTargetSendInternalIoctlSynchronously method builds an internal device control request and sends it synchronously to an I/O target.
old-location: wdf\wdfiotargetsendinternalioctlsynchronously.htm
old-project: wdf
ms.assetid: 4028b259-a157-4e50-b1a2-25da3050cced
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_c318553e-1a21-444e-b8e0-de4a1f17b98f.xml, WdfIoTargetSendInternalIoctlSynchronously, WdfIoTargetSendInternalIoctlSynchronously method, kmdf.wdfiotargetsendinternalioctlsynchronously, wdf.wdfiotargetsendinternalioctlsynchronously, wdfiotarget/WdfIoTargetSendInternalIoctlSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoTargetSendInternalIoctlSynchronously
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetSendInternalIoctlSynchronously function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetSendInternalIoctlSynchronously</b> method builds an internal device control request and sends it synchronously to an I/O target.


## -syntax


````
NTSTATUS WdfIoTargetSendInternalIoctlSynchronously(
  _In_      WDFIOTARGET               IoTarget,
  _In_opt_  WDFREQUEST                Request,
  _In_      ULONG                     IoctlCode,
  _In_opt_  PWDF_MEMORY_DESCRIPTOR    InputBuffer,
  _In_opt_  PWDF_MEMORY_DESCRIPTOR    OutputBuffer,
  _In_opt_  PWDF_REQUEST_SEND_OPTIONS RequestOptions,
  _Out_opt_ PULONG_PTR                BytesReturned
);
````


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param IoctlCode [in]

An I/O control code (IOCTL) that the I/O target supports. 


### -param InputBuffer [in, optional]

A pointer to a caller-allocated <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that describes a buffer that will be written to the I/O target. For more information, see the following Remarks section. This parameter is optional and can be <b>NULL</b> if the request does not send data.


### -param OutputBuffer [in, optional]

A pointer to a caller-allocated <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that describes a buffer that will receive data from the I/O target. For more information, see the following Remarks section. This parameter is optional and can be <b>NULL</b> if the request does not receive data.


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param BytesReturned [out, optional]

A pointer to a location that receives information (such as the number of bytes that were transferred) that another driver supplies when it completes the request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>. This pointer is optional and can be <b>NULL</b>.


## -returns



If the operation succeeds, <b>WdfIoTargetSendInternalIoctlSynchronously</b> returns after the internal device control request completes, and the return value is the request's completion status value. Otherwise, this method might return one of the following values:

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
The size of the WDF_REQUEST_SEND_OPTIONS structure that the <i>RequestOptions</i> parameter pointed to was incorrect.

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
The I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Use the <b>WdfIoTargetSendInternalIoctlSynchronously</b> method to send internal device control requests synchronously. To send internal device control requests asynchronously, use the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforinternalioctl.md">WdfIoTargetFormatRequestForInternalIoctl</a> method, followed by the <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a> method. 

For more information about internal device control requests, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.

The <b>WdfIoTargetSendInternalIoctlSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <i>RequestOptions</i> parameter's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure, or unless an error is detected.

You can forward an internal device control request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward an internal device control request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <b>WdfIoTargetSendInternalIoctlSynchronously</b> method's <i>Request</i> parameter.

</li>
<li>
Use the received request's input buffer for the <b>WdfIoTargetSendInternalIoctlSynchronously</b> method's <i>InputBuffer</i> parameter.

The driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a> to obtain a handle to the request's input buffer. The driver must then place that handle in the <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that the driver supplies for the <i>InputBuffer</i> parameter.

</li>
<li>
Use the received request's output buffer for the <b>WdfIoTargetSendInternalIoctlSynchronously</b> method's <i>OutputBuffer</i> parameter.

The driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to the request's output buffer, and it must then place that handle in the <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that the driver supplies for the <i>OutputBuffer</i> parameter.

</li>
</ol>
For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

<ol>
<li>
Supply a <b>NULL</b> request handle for the <b>WdfIoTargetSendInternalIoctlSynchronously</b> method's <i>Request</i> parameter, or create a new request object and supply its handle:<ul>
<li>If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.</li>
<li>If you call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. This technique enables your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.</li>
</ul>


Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

</li>
<li>
Provide buffer space for the <b>WdfIoTargetSendInternalIoctlSynchronously</b> method's <i>InputBuffer</i> and <i>OutputBuffer</i> parameters, if the request requires them. 

Your driver can specify this buffer space as locally allocated buffers, as WDFMEMORY handles, or as memory descriptor lists (MDLs). You can use whichever method is most convenient. 

If necessary, the framework converts the buffer descriptions so that they are correct for the IOCTL's transfer type. For more information about IOCTL transfer types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543023">Defining I/O Control Codes</a>. 

The following techniques to specify buffer space are available:

<ul>
<li>
Supply local buffers.

Because <b>WdfIoTargetSendInternalIoctlSynchronously</b> handles I/O requests synchronously, the driver can create request buffers that are local to the calling routine, as the following code example shows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  MemoryDescriptor;
MY_BUFFER_TYPE  MyBuffer;
WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(&amp;MemoryDescriptor,
                                  (PVOID) &amp;MyBuffer,
                                  sizeof(MyBuffer));</pre>
</td>
</tr>
</table></span></div>
</li>
<li>
Supply WDFMEMORY handles.

Call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> or <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a> to obtain a handle to framework-managed memory, as the following code example shows. 

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
                         &amp;MemoryHandle,
                         NULL);
WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(&amp;MemoryDescriptor,
                                  MemoryHandle,
                                  NULL);</pre>
</td>
</tr>
</table></span></div>
Alternatively, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a> or <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents a received I/O request's buffer, if you want the driver to pass that buffer's contents to the I/O target. The driver must not complete the received I/O request until the new request that <b>WdfIoTargetSendInternalIoctlSynchronously</b> sends to the I/O target has been deleted, reused, or reformatted. (<b>WdfIoTargetSendInternalIoctlSynchronously</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
<li>
Supply MDLs.

Drivers can obtain MDLs that are associated with a received I/O request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputwdmmdl.md">WdfRequestRetrieveInputWdmMdl</a> and <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>.

</li>
</ul>
</li>
</ol>
For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetSendInternalIoctlSynchronously</b>, see <a href="https://msdn.microsoft.com/3fa897f5-2de8-484b-becb-c2de23fb5e8c">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example defines a local buffer, initializes a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure, and calls <b>WdfIoTargetSendInternalIoctlSynchronously</b>. This example specifies <b>NULL</b> for the request object handle, so the framework will create a new request object for the I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_MEMORY_DESCRIPTOR  outputDescriptor;
NTSTATUS  status;
MY_DRIVER_INFORMATION  driverInformation;

WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(
                                  &amp;outputDescriptor,
                                  (PVOID) &amp;driverInformation,
                                  sizeof(MY_DRIVER_INFORMATION)
                                  );

status = WdfIoTargetSendInternalIoctlSynchronously(
                                                   hidTarget,
                                                   NULL,
                                                   IOCTL_INTERNAL_GET_MY_DRIVER_INFORMATION,
                                                   NULL,
                                                   &amp;outputDescriptor,
                                                   NULL,
                                                   NULL
                                                   );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputwdmmdl.md">WdfRequestRetrieveInputWdmMdl</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>



<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>



<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>



<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforinternalioctl.md">WdfIoTargetFormatRequestForInternalIoctl</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetSendInternalIoctlSynchronously method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

