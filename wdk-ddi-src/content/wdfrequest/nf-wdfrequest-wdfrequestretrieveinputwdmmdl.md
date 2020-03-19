---
UID: NF:wdfrequest.WdfRequestRetrieveInputWdmMdl
title: WdfRequestRetrieveInputWdmMdl function (wdfrequest.h)
description: The WdfRequestRetrieveInputWdmMdl method retrieves a memory descriptor list (MDL) that represents an I/O request's input buffer.
old-location: wdf\wdfrequestretrieveinputwdmmdl.htm
tech.root: wdf
ms.assetid: 8046d9e4-d4a2-4aeb-92b2-a48277af8b41
ms.date: 02/26/2018
keywords: ["WdfRequestRetrieveInputWdmMdl function"]
ms.keywords: DFRequestObjectRef_d65a1869-de52-4284-818f-a3f0837d0374.xml, WdfRequestRetrieveInputWdmMdl, WdfRequestRetrieveInputWdmMdl method, kmdf.wdfrequestretrieveinputwdmmdl, wdf.wdfrequestretrieveinputwdmmdl, wdfrequest/WdfRequestRetrieveInputWdmMdl
f1_keywords:
 - "wdfrequest/WdfRequestRetrieveInputWdmMdl"
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InputBufferAPI, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MdlAfterReqCompletedIntIoctl, MdlAfterReqCompletedIntIoctlA, MdlAfterReqCompletedIoctl, MdlAfterReqCompletedIoctlA, MdlAfterReqCompletedRead, MdlAfterReqCompletedWrite, MdlAfterReqCompletedWriteA
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
api_name:
- WdfRequestRetrieveInputWdmMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestRetrieveInputWdmMdl function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestRetrieveInputWdmMdl</b> method retrieves a memory descriptor list (MDL) that represents an I/O request's input buffer.


## -parameters




### -param Request [in]

A handle to a framework request object. 


### -param Mdl [out]

A pointer to a location that receives a pointer to an MDL.


## -returns



<b>WdfRequestRetrieveInputWdmMdl</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The input buffer's length is zero.

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



A request's input buffer contains information, such as data to be written to a disk, that was supplied by the originator of the request. Your driver can call <b>WdfRequestRetrieveInputWdmMdl</b> for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).

The <b>WdfRequestRetrieveInputWdmMdl</b> method retrieves the input buffer's MDL for I/O requests that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">buffered I/O</a> method or the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveInputWdmMdl</b> also supports I/O requests that use <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">neither buffered nor direct I/O</a>. 

If <b>WdfRequestRetrieveInputWdmMdl</b> returns STATUS_SUCCESS, the driver receives a pointer to an MDL that describes the input buffer. 

The driver must not access a request's MDL after <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completing the I/O request</a>.

For more information about <b>WdfRequestRetrieveInputWdmMdl</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

The following code example is part of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_write">EvtIoWrite</a> callback function that obtains an MDL for an I/O request's input buffer. If the call to <b>WdfRequestRetrieveInputWdmMdl</b> fails, the driver completes the request with the error status that <b>WdfRequestRetrieveInputWdmMdl</b> returns.

```cpp
VOID 
MyDrvEvtIoWrite(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  Length
    )
{
    NTSTATUS  status;
    PMDL  mdl = NULL;

...
    status = WdfRequestRetrieveInputWdmMdl(
                                           Request,
                                           &mdl
                                           );
    if (!NT_SUCCESS(status))
    {
        WdfRequestCompleteWithInformation(
                                          Request,
                                          status,
                                          0
                                          );
    }
...
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputwdmmdl">WdfRequestRetrieveOutputWdmMdl</a>
 

 

