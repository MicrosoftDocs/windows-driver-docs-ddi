---
UID: NF:wdfiotarget.WdfIoTargetSendInternalIoctlOthersSynchronously
title: WdfIoTargetSendInternalIoctlOthersSynchronously function
author: windows-driver-content
description: The WdfIoTargetSendInternalIoctlOthersSynchronously method builds a non-standard internal device control request and sends it synchronously to an I/O target.
old-location: wdf\wdfiotargetsendinternalioctlotherssynchronously.htm
old-project: wdf
ms.assetid: 53070b37-3836-49c2-91d1-369552afe214
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfIoTargetSendInternalIoctlOthersSynchronously
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
req.alt-api: WdfIoTargetSendInternalIoctlOthersSynchronously
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
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
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetSendInternalIoctlOthersSynchronously function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method builds a non-standard internal device control request and sends it synchronously to an I/O target.



## -syntax

````
NTSTATUS WdfIoTargetSendInternalIoctlOthersSynchronously(
  _In_      WDFIOTARGET               IoTarget,
  _In_opt_  WDFREQUEST                Request,
  _In_      ULONG                     IoctlCode,
  _In_opt_  PWDF_MEMORY_DESCRIPTOR    OtherArg1,
  _In_opt_  PWDF_MEMORY_DESCRIPTOR    OtherArg2,
  _In_opt_  PWDF_MEMORY_DESCRIPTOR    OtherArg4,
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


### -param OtherArg1 [in, optional]

A pointer to a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure that describes a memory buffer that contains context information. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg2 [in, optional]

A pointer to a WDF_MEMORY_DESCRIPTOR structure that describes a memory buffer that contains context information. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg4 [in, optional]

A pointer to a WDF_MEMORY_DESCRIPTOR structure that describes a memory buffer that contains context information. This parameter is optional and can be <b>NULL</b>.


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.


### -param BytesReturned [out, optional]

A pointer to a location that receives information (such as the number of bytes that were transferred) that another driver supplies when it completes the request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>. This pointer is optional and can be <b>NULL</b>.


## -returns
If the operation succeeds, <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> returns after the internal device control request completes, and the return value is the request's completion status value. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid parameter was detected.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter pointed to was incorrect.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The request was already queued to an I/O target.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The framework could not allocate system resources (typically memory).
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>The driver supplied a time-out value and the request did not complete within the allotted time.
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>The I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
A non-standard internal device control request uses an IOCTL code to identify the operation to be performed, but the request does not use the standard input and output buffers that other internal device control requests use. If you are creating a set of interacting drivers, you can define how this set of drivers use the request's arguments: <i>OtherArg1</i>, <i>OtherArg2</i>, and <i>OtherArg4</i>. 

There is no parameter called <i>OtherArg3</i> because the framework associates these parameters with the <b>Argument1</b>, <b>Argument2</b>, and <b>Argument4</b> members of the <b>Other.Parameters</b> union in the driver's <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure. The <b>Argument3</b> member in that union receives the value from the <i>IoctlCode</i> parameter, so it is  not available for other driver-supplied values.

Use the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method to send non-standard internal device control requests synchronously. To send internal device control requests asynchronously, use <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforinternalioctlothers.md">WdfIoTargetFormatRequestForInternalIoctlOthers</a>, followed by <a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>. 

For more information about internal device control requests, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.

The <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <i>RequestOptions</i> parameter's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a> structure, or unless an error is detected.

You can forward a non-standard internal device control request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and possibly some context space.

To forward a non-standard internal device control request that your driver received in an I/O queue:

Specify the received request's handle for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>Request</i> parameter.

Use the received request's context information for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>OtherArg1</i>,<i>OtherArg2</i>, and<i>OtherArg4</i> parameters.

To obtain these parameter values, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a> and use the <b>DeviceIoControl</b> member of the <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a> structure that is returned. 

For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

Supply a <b>NULL</b> request handle for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>Request</i> parameter, or create a new request object and supply its handle:<ul>
<li>If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.</li>
<li>If you call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>. This technique enables your driver's <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.</li>
</ul>


Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

Provide context space for the <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> method's <i>OtherArg1</i>,<i>OtherArg2</i>, and <i>OtherArg4</i> parameters, if the request requires them.

Your driver can specify this context space as locally allocated buffers, as WDFMEMORY handles, or as memory descriptor lists (MDLs). You can use whichever method is most convenient. 

The following techniques to specify buffer space are available:

Supply local buffers.

Because <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b> handles I/O requests synchronously, the driver can create request buffers that are local to the calling routine, as the following code example shows.

Supply WDFMEMORY handles.

Call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> or <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a> to obtain a handle to framework-managed memory, as the following code example shows. 

Supply MDLs.

Drivers can obtain MDLs that are associated with a received I/O request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputwdmmdl.md">WdfRequestRetrieveInputWdmMdl</a> and <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>.

For information about obtaining status information after an I/O request completes, see <a href="wdf.completing_i_o_requests#obtaining_completion_information#obtaining_completion_information">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b>, see <a href="https://msdn.microsoft.com/3fa897f5-2de8-484b-becb-c2de23fb5e8c">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.

The following code example initializes an IEEE 1394 IRB structure, uses the structure's address to initialize a <a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a> structure, and then calls <b>WdfIoTargetSendInternalIoctlOthersSynchronously</b>. 


## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="..\wdfmemory\ns-wdfmemory-_wdf_memory_descriptor.md">WDF_MEMORY_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_buffer.md">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>
</dt>
<dt>
<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_parameters.md">WDF_REQUEST_PARAMETERS</a>
</dt>
<dt>
<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_send_options.md">WDF_REQUEST_SEND_OPTIONS</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforinternalioctlothers.md">WdfIoTargetFormatRequestForInternalIoctlOthers</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a>
</dt>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreatepreallocated.md">WdfMemoryCreatePreallocated</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcancelsentrequest.md">WdfRequestCancelSentRequest</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreate.md">WdfRequestCreate</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputwdmmdl.md">WdfRequestRetrieveInputWdmMdl</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputwdmmdl.md">WdfRequestRetrieveOutputWdmMdl</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestsend.md">WdfRequestSend</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetSendInternalIoctlOthersSynchronously method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

