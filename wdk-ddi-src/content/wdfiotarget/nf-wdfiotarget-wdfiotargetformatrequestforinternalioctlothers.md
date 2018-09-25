---
UID: NF:wdfiotarget.WdfIoTargetFormatRequestForInternalIoctlOthers
title: WdfIoTargetFormatRequestForInternalIoctlOthers function
author: windows-driver-content
description: The WdfIoTargetFormatRequestForInternalIoctlOthers method builds a non-standard internal device control request for an I/O target but does not send the request.
old-location: wdf\wdfiotargetformatrequestforinternalioctlothers.htm
tech.root: wdf
ms.assetid: e843eb33-f688-4963-9f35-244b4ed0ef7a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_bf839577-4858-4b98-adf3-cee7e8f01bd5.xml, WdfIoTargetFormatRequestForInternalIoctlOthers, WdfIoTargetFormatRequestForInternalIoctlOthers method, kmdf.wdfiotargetformatrequestforinternalioctlothers, wdf.wdfiotargetformatrequestforinternalioctlothers, wdfiotarget/WdfIoTargetFormatRequestForInternalIoctlOthers
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoTargetFormatRequestForInternalIoctlOthers
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetFormatRequestForInternalIoctlOthers function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> method builds a non-standard internal device control request for an I/O target but does not send the request.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>, or from a method that a specialized I/O target supplies.


### -param Request [in]

A handle to a framework request object. For more information, see the following Remarks section.


### -param IoctlCode [in]

An I/O control code (IOCTL) that the I/O target supports. 


### -param OtherArg1 [in, optional]

A handle to a framework memory object. This object represents a buffer that the driver uses for request-specific, driver-defined context information. For more information, see the following Remarks section. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg1Offset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. Drivers can use these values to specify the beginning address and length of a segment of the context area that is specified by <i>OtherArg1</i>. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg2 [in, optional]

A handle to a framework memory object. This object represents a buffer that the driver uses for request-specific, driver-defined context information. For more information, see the following Remarks section. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg2Offset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. Drivers can use these values to specify the beginning address and length of a segment of the context area that is specified by <i>OtherArg2</i>. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg4 [in, optional]

A handle to a framework memory object. This object represents a buffer that the driver uses for request-specific, driver-defined context information. For more information, see the following Remarks section. This parameter is optional and can be <b>NULL</b>.


### -param OtherArg4Offset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. Drivers can use these values to specify the beginning address and length of a segment of the context area that is specified by <i>OtherArg4</i>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The transfer length was larger than the buffer length, or the I/O request was already queued to an I/O target.

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



Use the <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> method, followed by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> method, to send non-standard internal device control requests either synchronously or asynchronously. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a> method to send non-standard internal device control requests synchronously. 

You can forward a non-standard internal device control request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward a non-standard internal device control request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> method's <i>Request</i> parameter.

</li>
<li>
Use the received request's context information for the <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> method's <i>OtherArg1</i>, <i>OtherArg2</i>, an <i>OtherArg4</i> parameters.

To obtain these parameter values, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a> and use the <b>DeviceIoControl</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a> structure that is returned. 

</li>
</ol>
For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

<ol>
<li>
Create a new request object and supply its handle for the <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> method's <i>Request</i> parameter.

Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> to preallocate one or more request objects. You can reuse these request objects by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>. Your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can preallocate request objects for a device.

</li>
<li>
Provide context buffers, if the request requires them, and supply buffer handles for the <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> method's <i>OtherArg1</i>, <i>OtherArg2</i>, and <i>OtherArg4</i> parameters.

Your driver must specify this buffer space as WDFMEMORY handles to framework-managed memory. To obtain WDFMEMORY handles, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a>. 

</li>
</ol>
After a driver calls <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> to format a device control request, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request (either synchronously or asynchronously) to an I/O target.

Multiple calls to <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> that use the same request do not cause additional resource allocations. Therefore, to reduce the chance that <a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a> will return STATUS_INSUFFICIENT_RESOURCES, your driver's <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function can call <b>WdfRequestCreate</b> to preallocate one or more request objects for a device. The driver can subsequently reuse (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>), reformat (call <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b>), and resend (call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>) each request object without risking a STATUS_INSUFFICIENT_RESOURCES return value from a later call to <b>WdfRequestCreate</b>. (If the driver does not call the same request-formatting method each time, additional resources might be allocated.) All subsequent calls to <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b> for the reused request object will return STATUS_SUCCESS, if parameter values do not change.

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about <b>WdfIoTargetFormatRequestForInternalIoctlOthers</b>, see <a href="https://msdn.microsoft.com/3fa897f5-2de8-484b-becb-c2de23fb5e8c">Sending I/O Requests to General I/O Targets</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example creates a framework memory object, obtains the buffer that the memory object contains, and initializes the buffer. Then, the example formats the request, sets a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function, and sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PIRB pIrb;
WDFMEMORY memory;
NTSTATUS status;

status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         sizeof(IRB),
                         &amp;memory,
                         NULL
                         );
if (!NT_SUCCESS(status)) {
    goto Done;
}
pIrb = WdfMemoryGetBuffer(
                          memory,
                          NULL
                          );

pIrb-&gt;FunctionNumber = REQUEST_ALLOCATE_ADDRESS_RANGE;
pIrb-&gt;Flags = 0;
pIrb-&gt;u.AllocateAddressRange.Mdl = pAsyncAddressData-&gt;pMdl;
pIrb-&gt;u.AllocateAddressRange.fulFlags = fulFlags;
pIrb-&gt;u.AllocateAddressRange.nLength = nLength;
pIrb-&gt;u.AllocateAddressRange.MaxSegmentSize = MaxSegmentSize;
pIrb-&gt;u.AllocateAddressRange.fulAccessType = fulAccessType;
pIrb-&gt;u.AllocateAddressRange.fulNotificationOptions = fulNotificationOptions;
pIrb-&gt;u.AllocateAddressRange.Callback = NULL;
pIrb-&gt;u.AllocateAddressRange.Context = NULL;
pIrb-&gt;u.AllocateAddressRange.Required1394Offset = *Required1394Offset;
pIrb-&gt;u.AllocateAddressRange.FifoSListHead = NULL;
pIrb-&gt;u.AllocateAddressRange.FifoSpinLock = NULL;
pIrb-&gt;u.AllocateAddressRange.AddressesReturned = 0;
pIrb-&gt;u.AllocateAddressRange.p1394AddressRange = pAsyncAddressData-&gt;AddressRange;
pIrb-&gt;u.AllocateAddressRange.DeviceExtension = deviceExtension;

status = WdfIoTargetFormatRequestForInternalIoctlOthers(
                                                        IoTarget,
                                                        Request,
                                                        IOCTL_1394_CLASS,
                                                        memory,
                                                        NULL,
                                                        NULL,
                                                        NULL,
                                                        NULL,
                                                        NULL
                                                        );

if (!NT_SUCCESS(status)) {
    goto Done;
}

WdfRequestSetCompletionRoutine(
                               Request,
                               MyRequestCompletion,
                               NULL
                               );

if (WdfRequestSend(
                   Request,
                   IoTarget,
                   NULL
                   ) == FALSE) {
    status = WdfRequestGetStatus(Request);
}
else {
    status = STATUS_SUCCESS;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552472">WDF_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548712">WdfMemoryCreatePreallocated</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>
 

 

