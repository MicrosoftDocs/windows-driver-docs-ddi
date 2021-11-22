---
UID: NF:wdfrequest.WdfRequestProbeAndLockUserBufferForWrite
title: WdfRequestProbeAndLockUserBufferForWrite function (wdfrequest.h)
description: The WdfRequestProbeAndLockUserBufferForWrite method verifies that an I/O request's user-mode buffer is writeable, and then it locks the buffer's physical memory pages so drivers in the driver stack can write into the buffer.
old-location: wdf\wdfrequestprobeandlockuserbufferforwrite.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfRequestProbeAndLockUserBufferForWrite function"]
ms.keywords: DFRequestObjectRef_8a3643bf-a6b6-4e22-baa8-bfb8a5716af6.xml, WdfRequestProbeAndLockUserBufferForWrite, WdfRequestProbeAndLockUserBufferForWrite method, kmdf.wdfrequestprobeandlockuserbufferforwrite, wdf.wdfrequestprobeandlockuserbufferforwrite, wdfrequest/WdfRequestProbeAndLockUserBufferForWrite
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
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
 - WdfRequestProbeAndLockUserBufferForWrite
 - wdfrequest/WdfRequestProbeAndLockUserBufferForWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfRequestProbeAndLockUserBufferForWrite
---

# WdfRequestProbeAndLockUserBufferForWrite function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfRequestProbeAndLockUserBufferForWrite</b> method verifies that an I/O request's user-mode buffer is writeable, and then it locks the buffer's physical memory pages so drivers in the driver stack can write into the buffer.

## -parameters

### -param Request [in]


A handle to a framework request object.

### -param Buffer [in]


A pointer to the request's output buffer. For more information, see the following Remarks section.

### -param Length [in]


The length, in bytes, of the request's output buffer.

### -param MemoryObject [out]


A pointer to a location that receives a handle to a framework memory object that represents the user output buffer.

## -returns

<b>WdfRequestProbeAndLockUserBufferForWrite</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Length</i> parameter is zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request has already been completed or is otherwise invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>
</td>
<td width="60%">
The current thread is not the creator of the I/O request.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory to complete the operation.

</td>
</tr>
</table>
 

This method might also return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.

## -remarks

The user output buffer typically receives information that the driver has read from the device.

Only a top-level driver can call the <b>WdfRequestProbeAndLockUserBufferForWrite</b> method, because the method requires the process context of the process that created the I/O request.

The user-mode buffer that the <i>Buffer</i> parameter specifies can be the buffer that <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveunsafeuseroutputbuffer">WdfRequestRetrieveUnsafeUserOutputBuffer</a> retrieves, or it can be a different user-mode output buffer. For example, an I/O control code that uses the buffered access method might pass a structure that contains an embedded pointer to a user-mode buffer. In such a case, the driver can use<b>WdfRequestProbeAndLockUserBufferForWrite</b> to obtain a memory object for the buffer. 

The buffer length that the <i>Length</i> parameter specifies must not be larger than the buffer's actual size. Otherwise, drivers can access memory outside of the buffer, which is a security risk.

If <b>WdfRequestProbeAndLockUserBufferForWrite</b> returns STATUS_SUCCESS, the driver receives a handle to a framework memory object that represents the user-mode buffer. To access the buffer, the driver must call <a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>.

The framework memory object is automatically released when the driver calls [**WdfRequestComplete**](./nf-wdfrequest-wdfrequestcomplete.md).

For more information about <b>WdfRequestProbeAndLockUserBufferForWrite</b>, see <a href="/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfRequestProbeAndLockUserBufferForWrite</b>, see <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestprobeandlockuserbufferforread">WdfRequestProbeAndLockUserBufferForRead</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestprobeandlockuserbufferforread">WdfRequestProbeAndLockUserBufferForRead</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveunsafeuseroutputbuffer">WdfRequestRetrieveUnsafeUserOutputBuffer</a>