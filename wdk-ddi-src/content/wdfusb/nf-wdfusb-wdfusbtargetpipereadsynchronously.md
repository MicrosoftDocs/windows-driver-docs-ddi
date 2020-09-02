---
UID: NF:wdfusb.WdfUsbTargetPipeReadSynchronously
title: WdfUsbTargetPipeReadSynchronously function (wdfusb.h)
description: The WdfUsbTargetPipeReadSynchronously method builds a read request and sends it synchronously to a specified USB input pipe.
old-location: wdf\wdfusbtargetpipereadsynchronously.htm
tech.root: wdf
ms.assetid: e09f68bd-cd43-42ce-988e-505415d62891
ms.date: 02/26/2018
keywords: ["WdfUsbTargetPipeReadSynchronously function"]
ms.keywords: DFUsbRef_97551c52-37b0-4ed7-a961-921ed0e990b6.xml, WdfUsbTargetPipeReadSynchronously, WdfUsbTargetPipeReadSynchronously method, kmdf.wdfusbtargetpipereadsynchronously, wdf.wdfusbtargetpipereadsynchronously, wdfusb/WdfUsbTargetPipeReadSynchronously
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InternalIoctlReqs, IoctlReqs, KmdfIrql, KmdfIrql2, SyncReqSend, UsbKmdfIrql, UsbKmdfIrql2, WriteReqs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfUsbTargetPipeReadSynchronously
 - wdfusb/WdfUsbTargetPipeReadSynchronously
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfUsbTargetPipeReadSynchronously
---

# WdfUsbTargetPipeReadSynchronously function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetPipeReadSynchronously</b> method builds a read request and sends it synchronously to a specified USB input pipe.

## -parameters

### -param Pipe 

[in]
A handle to a framework pipe object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>.

### -param Request 

[in, optional]
A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

### -param RequestOptions 

[in, optional]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section.

### -param MemoryDescriptor 

[in, optional]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure that describes the buffer that will receive data from the device. The buffer size must be a multiple of the pipe's maximum packet size unless the driver has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipesetnomaximumpacketsizecheck">WdfUsbTargetPipeSetNoMaximumPacketSizeCheck</a>. For more information about this buffer, see the following Remarks section.

### -param BytesRead 

[out, optional]
A pointer to a location that receives the number of bytes that were read, if the operation succeeds. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>WdfUsbTargetPipeReadSynchronously</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that was pointed to by <i>RequestOptions</i> was incorrect.

</td>
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
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory was available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The caller's IRQL was not PASSIVE_LEVEL, an invalid memory descriptor was specified, the pipe's type was not valid, the transfer direction was invalid, or the specified I/O request was already queued to an I/O target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_BUFFER_SIZE</b></dt>
</dl>
</td>
<td width="60%">
The buffer size was not a multiple of the pipe's maximum packet size.

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
The I/O request packet (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>) that the <i>Request</i> parameter represents does not provide enough <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structures to allow the driver to forward the request.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

Use the <b>WdfUsbTargetPipeReadSynchronously</b> method to send read requests synchronously. To send read requests asynchronously, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipeformatrequestforread">WdfUsbTargetPipeFormatRequestForRead</a>, followed by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>.

The pipe that the <i>Pipe</i> parameter specifies must be an input pipe, and the pipe's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-get_type">type</a> must be <b>WdfUsbPipeTypeBulk</b> or <b>WdfUsbPipeTypeInterrupt</b>.

The <b>WdfUsbTargetPipeReadSynchronously</b> method does not return until the request has completed, unless the driver supplies a time-out value in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a> structure that the <i>RequestOptions</i> parameter points to, or unless an error is detected.

You can forward an I/O request that your driver received in an I/O queue, or you can create and send a new request. In either case, the framework requires a request object and some buffer space.

To forward an I/O request that your driver received in an I/O queue:

<ol>
<li>
Specify the received request's handle for the <i>Request</i> parameter.

</li>
<li>
Use the received request's output buffer for the <b>WdfUsbTargetPipeReadSynchronously</b> method's <i>MemoryDescriptor</i> parameter.

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents the request's output buffer and then place that handle in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure that <i>MemoryDescriptor</i> points to.

</li>
</ol>
For more information about forwarding an I/O request, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.

Drivers often divide received I/O requests into smaller requests that they send to an I/O target, so your driver might create new requests.

To create a new I/O request:

<ol>
<li>
Supply a <b>NULL</b> request handle in the <b>WdfUsbTargetPipeReadSynchronously</b> method's <i>Request</i> parameter, or create a new request object and supply its handle:<ul>
<li>If you supply a <b>NULL</b> request handle, the framework uses an internal request object. This technique is simple to use, but the driver cannot cancel the request.</li>
<li>If you call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcreate">WdfRequestCreate</a> to create one or more request objects, you can reuse these request objects by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestreuse">WdfRequestReuse</a>. This technique enables your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function to preallocate request objects for a device. Additionally, another driver thread can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestcancelsentrequest">WdfRequestCancelSentRequest</a> to cancel the request, if necessary.</li>
</ul>


Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

</li>
<li>
Provide buffer space for the <b>WdfUsbTargetPipeReadSynchronously</b> method's <i>MemoryDescriptor</i> parameter.

Your driver can specify this buffer space as a locally allocated buffer, as a WDFMEMORY handle, or as an MDL. You can use whichever method is most convenient. 

If necessary, the framework converts the buffer description to one that is correct for the I/O target's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">method for accessing data buffers</a>. 

The following techniques are available:

<ul>
<li>
Supply a local buffer

Because <b>WdfUsbTargetPipeReadSynchronously</b> handles I/O requests synchronously, the driver can create request buffers that are local to the calling routine, as the following code example shows.

```cpp
WDF_MEMORY_DESCRIPTOR  memoryDescriptor;
MY_BUFFER_TYPE  myBuffer;
WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(&memoryDescriptor,
                                  (PVOID) &myBuffer,
                                  sizeof(myBuffer));
```
</li>
<li>
Supply a WDFMEMORY handle

Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreatepreallocated">WdfMemoryCreatePreallocated</a> to obtain a handle to framework-managed memory, as the following code example shows. 

```cpp
WDF_MEMORY_DESCRIPTOR  memoryDescriptor;
WDFMEMORY  memoryHandle = NULL;
status = WdfMemoryCreate(NULL,
                         NonPagedPool,
                         POOL_TAG,
                         MY_BUFFER_SIZE,
                         &memoryHandle,
                         NULL);
WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(&memoryDescriptor,
                                  memoryHandle,
                                  NULL);
```
Alternatively, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputmemory">WdfRequestRetrieveOutputMemory</a> to obtain a handle to a framework memory object that represents a received I/O request's output buffer, if you want the driver to pass that buffer's contents to the I/O target. The driver must not complete the received I/O request until the new request that <b>WdfUsbTargetPipeReadSynchronously</b> sends to the I/O target has been deleted, reused, or reformatted. (<b>WdfUsbTargetPipeReadSynchronously</b> increments the memory object's reference count. Deleting, reusing, or reformatting a request object decrements the memory object's reference count.)

</li>
<li>
Supply an MDL

Drivers can obtain the MDL that is associated with a received I/O request by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputwdmmdl">WdfRequestRetrieveOutputWdmMdl</a>.

</li>
</ul>
</li>
</ol>
The framework sets the USBD_SHORT_TRANSFER_OK flag in its internal <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>. Setting this flag allows the last packet of a data transfer to be less than the maximum packet size.

A driver cannot call <b>WdfUsbTargetPipeReadSynchronously</b> if it has configured a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/working-with-usb-pipes">continuous reader</a> for the pipe.

For information about obtaining status information after an I/O request completes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">Obtaining Completion Information</a>.

For more information about the <b>WdfUsbTargetPipeReadSynchronously</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example creates a framework memory object, initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/ns-wdfmemory-_wdf_memory_descriptor">WDF_MEMORY_DESCRIPTOR</a> structure, and passes the structure to <b>WdfUsbTargetPipeReadSynchronously</b>. This example specifies <b>NULL</b> for the request object handle, so the framework will create a new request object for the I/O target.

```cpp
WDFMEMORY  wdfMemory;
WDF_MEMORY_DESCRIPTOR  readBufDesc;
ULONG  BytesRead;

status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         readSize,
                         &wdfMemory,
                         NULL
                         );
if (!NT_SUCCESS(status)){
    return ;
}

buffer = WdfMemoryGetBuffer(
                            wdfMemory,
                            NULL
                            );

WDF_MEMORY_DESCRIPTOR_INIT_BUFFER(
                                  &readBufDesc,
                                  buffer,
                                  readSize
                                  );

status = WdfUsbTargetPipeReadSynchronously(
                                           Pipe,
                                           NULL,
                                           NULL,
                                           &readBufDesc,
                                           &BytesRead
                                           );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdf_memory_descriptor_init_buffer">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetpipegetinformation">WdfUsbTargetPipeGetInformation</a>

