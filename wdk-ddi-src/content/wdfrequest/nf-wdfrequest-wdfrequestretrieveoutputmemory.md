---
UID: NF:wdfrequest.WdfRequestRetrieveOutputMemory
title: WdfRequestRetrieveOutputMemory function (wdfrequest.h)
description: The WdfRequestRetrieveOutputMemory method retrieves a handle to a framework memory object that represents an I/O request's output buffer.
old-location: wdf\wdfrequestretrieveoutputmemory.htm
tech.root: wdf
ms.assetid: c61e343a-5276-4cb8-87ff-9852ad167ff5
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_fdcaef98-5478-42af-a61e-669eec37907e.xml, WdfRequestRetrieveOutputMemory, WdfRequestRetrieveOutputMemory method, kmdf.wdfrequestretrieveoutputmemory, wdf.wdfrequestretrieveoutputmemory, wdfrequest/WdfRequestRetrieveOutputMemory
ms.topic: function
f1_keywords:
 - "wdfrequest/WdfRequestRetrieveOutputMemory"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MemAfterReqCompletedIntIoctl, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctl, MemAfterReqCompletedIoctlA, MemAfterReqCompletedRead, MemAfterReqCompletedReadA, MemAfterReqCompletedWrite, OutputBufferAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
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
- WdfRequestRetrieveOutputMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestRetrieveOutputMemory function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestRetrieveOutputMemory</b> method retrieves a handle to a framework memory object that represents an I/O request's output buffer.


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param Memory [out]

A pointer to a location that receives a handle to a framework memory object. 


## -returns



<b>WdfRequestRetrieveOutputMemory</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The output buffer's length is zero.

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



A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <b>WdfRequestRetrieveOutputMemory</b> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <b>WdfRequestRetrieveOutputMemory</b> method retrieves the output buffer for I/O requests that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">buffered I/O</a> method or the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveOutputMemory</b> also supports I/O requests that use <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">neither buffered nor direct I/O</a>. 

If <b>WdfRequestRetrieveOutputMemory</b> returns STATUS_SUCCESS, the driver receives a handle to a framework memory object that represents the output buffer. To access the buffer, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>. 

The driver can access the retrieved framework memory object until it <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

Instead of calling <b>WdfRequestRetrieveOutputMemory</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">WdfRequestRetrieveOutputBuffer</a>, which retrieves the buffer's address and length.

For more information about <b>WdfRequestRetrieveOutputMemory</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfio/nc-wdfio-evt_wdf_io_queue_io_read">EvtIoRead</a> callback function can obtain a handle to the framework memory object that represents a read request's output buffer. The example then formats and sends the read request to a USB I/O target. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID 
MyEvtIoRead(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
    WDFUSBPIPE  pipe;
    NTSTATUS  status;
    WDFMEMORY  reqMemory;
    PDEVICE_CONTEXT  pDeviceContext;

    //
    // The driver previously stored a pipe handle in 
    // the device object's context space.
    //
    pDeviceContext = GetDeviceContext(WdfIoQueueGetDevice(Queue));
    pipe = pDeviceContext->BulkReadPipe;

    //
    // Get output memory.
    //
    status = WdfRequestRetrieveOutputMemory(
                                            Request,
                                            &reqMemory
                                            );
    if(!NT_SUCCESS(status)){
        goto Exit;
    }
    //
    // Format the request.
    //
    status = WdfUsbTargetPipeFormatRequestForRead(
                                           pipe,
                                           Request,
                                           reqMemory,
                                           NULL
                                           ); 
    if (!NT_SUCCESS(status)) {
        goto Exit;
    }
    WdfRequestSetCompletionRoutine(
                                   Request,
                                   EvtRequestReadCompletionRoutine,
                                   pipe
                                   );
    //
    // Send the request.
    //
    if (WdfRequestSend(
                       Request,
                       WdfUsbTargetPipeGetIoTarget(pipe),
                       WDF_NO_SEND_OPTIONS
                       ) == FALSE) {
        status = WdfRequestGetStatus(Request);
        goto Exit;
    }
Exit:
    //
    // Complete the request now if an error occurred.
    //
    if (!NT_SUCCESS(status)) {
        WdfRequestCompleteWithInformation(
                                          Request,
                                          status,
                                          0
                                          );
    }
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">WdfRequestRetrieveOutputBuffer</a>
 

 

