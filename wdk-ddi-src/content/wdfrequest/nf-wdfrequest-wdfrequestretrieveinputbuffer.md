---
UID: NF:wdfrequest.WdfRequestRetrieveInputBuffer
title: WdfRequestRetrieveInputBuffer function (wdfrequest.h)
description: The WdfRequestRetrieveInputBuffer method retrieves an I/O request's input buffer.
old-location: wdf\wdfrequestretrieveinputbuffer.htm
tech.root: wdf
ms.assetid: fa02a787-502c-48a3-a5e1-710d7513c42e
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_7b0c1902-f3a3-4b89-8a9d-3e05e1639fd3.xml, WdfRequestRetrieveInputBuffer, WdfRequestRetrieveInputBuffer method, kmdf.wdfrequestretrieveinputbuffer, wdf.wdfrequestretrieveinputbuffer, wdfrequest/WdfRequestRetrieveInputBuffer
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestRetrieveInputBuffer"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedWrite, BufAfterReqCompletedWriteA, DriverCreate, InputBufferAPI, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
- WdfRequestRetrieveInputBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestRetrieveInputBuffer function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestRetrieveInputBuffer</b> method retrieves an I/O request's input buffer.


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param MinimumRequiredLength

<p>The minimum buffer size, in bytes, that the driver needs to process the I/O request.</p>


### -param Buffer [out]

A pointer to a location that receives the buffer's address.


### -param Length [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfRequestRetrieveInputBuffer</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The input buffer's length is zero, or the <i>MinimumRequiredSize</i> parameter specifies a buffer size that is larger than the buffer's actual size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request type is not valid or the request is using <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">neither buffered nor direct I/O</a>. For more information about supported methods for accessing data buffers, see the following Remarks section.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The request has already been completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory.

</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A request's input buffer contains information, such as data to be written to a disk, that was supplied by the originator of the request. Your driver can call <b>WdfRequestRetrieveInputBuffer</b> to obtain the input buffer for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).

The <b>WdfRequestRetrieveInputBuffer</b> method retrieves the input buffer for I/O requests that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">buffered I/O</a> method or the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveInputBuffer</b> also supports I/O requests that use <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">neither buffered nor direct I/O</a>. 

If <b>WdfRequestRetrieveInputBuffer</b> returns STATUS_SUCCESS, the driver receives the address and, optionally, the size of the input buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

Instead of calling <b>WdfRequestRetrieveInputBuffer</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about <b>WdfRequestRetrieveInputBuffer</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

The following code example is part of the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">Serial</a> sample driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_device_control">EvtIoDeviceControl</a> callback function. If the I/O control code is IOCTL_SERIAL_SET_TIMEOUT, the driver obtains new time-out values from the I/O request's input buffer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
SerialEvtIoDeviceControl(
    IN WDFQUEUE     Queue,
    IN WDFREQUEST   Request,
    IN size_t       OutputBufferLength,
    IN size_t       InputBufferLength,
    IN ULONG        IoControlCode
    )
{
    PVOID  buffer;
    size_t  bufSize;

    switch (IoControlCode) {
...

        case IOCTL_SERIAL_SET_TIMEOUTS: {

            PSERIAL_TIMEOUTS NewTimeouts;

            Status = WdfRequestRetrieveInputBuffer(
                                                   Request,
                                                   sizeof(SERIAL_TIMEOUTS),
                                                   &buffer,
                                                   &bufSize
                                                   );
            if (!NT_SUCCESS(Status)) {
                break;
            }

            NewTimeouts =(PSERIAL_TIMEOUTS)buffer;
    }
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">WdfRequestRetrieveOutputBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceretrieveconfigdescriptor">WdfUsbTargetDeviceRetrieveConfigDescriptor</a>
 

 

