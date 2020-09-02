---
UID: NF:wdfrequest.WdfRequestRetrieveUnsafeUserInputBuffer
title: WdfRequestRetrieveUnsafeUserInputBuffer function (wdfrequest.h)
description: The WdfRequestRetrieveUnsafeUserInputBuffer method retrieves an I/O request's input buffer, if the request's technique for accessing data buffers is neither buffered nor direct I/O.
old-location: wdf\wdfrequestretrieveunsafeuserinputbuffer.htm
tech.root: wdf
ms.assetid: 0a5e141d-2ef5-482c-8470-560411241510
ms.date: 02/26/2018
keywords: ["WdfRequestRetrieveUnsafeUserInputBuffer function"]
ms.keywords: DFRequestObjectRef_0ac5a2ff-74b6-4e9c-9a3e-0038c3e1420a.xml, WdfRequestRetrieveUnsafeUserInputBuffer, WdfRequestRetrieveUnsafeUserInputBuffer method, kmdf.wdfrequestretrieveunsafeuserinputbuffer, wdf.wdfrequestretrieveunsafeuserinputbuffer, wdfrequest/WdfRequestRetrieveUnsafeUserInputBuffer
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedWrite, BufAfterReqCompletedWriteA, DriverCreate, InputBufferAPI, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestRetrieveUnsafeUserInputBuffer
 - wdfrequest/WdfRequestRetrieveUnsafeUserInputBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfRequestRetrieveUnsafeUserInputBuffer
---

# WdfRequestRetrieveUnsafeUserInputBuffer function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestRetrieveUnsafeUserInputBuffer</b> method retrieves an I/O request's input buffer, if the request's technique for accessing data buffers is <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">neither buffered nor direct I/O</a>.

## -parameters

### -param Request 

[in]
A handle to a framework request object.

### -param MinimumRequiredLength 

[in]
The minimum buffer size, in bytes, that the driver needs to process the I/O request.

### -param InputBuffer 

[out]
A pointer to a location that receives the buffer's address.

### -param Length 

[out, optional]
A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>WdfRequestRetrieveUnsafeUserInputBuffer</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
This value is returned if one of the following occurs:

<ul>
<li>
The method was not called from within the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function.

</li>
<li>
The I/O request's I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>.

</li>
<li>
The request specifies <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">buffered I/O</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">direct I/O</a>.

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>MinimumRequiredLength</i> parameter specifies a buffer size that is larger than the buffer's actual size.

</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The <b>WdfRequestRetrieveUnsafeUserInputBuffer</b> method must be called from an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a> callback function. After calling <b>WdfRequestRetrieveUnsafeUserInputBuffer</b>, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestprobeandlockuserbufferforread">WdfRequestProbeAndLockUserBufferForRead</a>. 

The driver can call <b>WdfRequestRetrieveUnsafeUserInputBuffer</b> if a request's I/O control code is <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

For more information about <b>WdfRequestRetrieveUnsafeUserInputBuffer</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfRequestRetrieveUnsafeUserInputBuffer</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestprobeandlockuserbufferforread">WdfRequestProbeAndLockUserBufferForRead</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_io_in_caller_context">EvtIoInCallerContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestprobeandlockuserbufferforread">WdfRequestProbeAndLockUserBufferForRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveunsafeuseroutputbuffer">WdfRequestRetrieveUnsafeUserOutputBuffer</a>

