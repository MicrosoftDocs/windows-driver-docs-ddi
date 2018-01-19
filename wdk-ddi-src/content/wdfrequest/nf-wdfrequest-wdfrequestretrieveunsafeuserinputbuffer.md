---
UID: NF:wdfrequest.WdfRequestRetrieveUnsafeUserInputBuffer
title: WdfRequestRetrieveUnsafeUserInputBuffer function
author: windows-driver-content
description: The WdfRequestRetrieveUnsafeUserInputBuffer method retrieves an I/O request's input buffer, if the request's technique for accessing data buffers is neither buffered nor direct I/O.
old-location: wdf\wdfrequestretrieveunsafeuserinputbuffer.htm
old-project: wdf
ms.assetid: 0a5e141d-2ef5-482c-8470-560411241510
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestRetrieveUnsafeUserInputBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfRequestRetrieveUnsafeUserInputBuffer
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
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
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestRetrieveUnsafeUserInputBuffer function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestRetrieveUnsafeUserInputBuffer</b> method retrieves an I/O request's input buffer, if the request's technique for accessing data buffers is <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>.



## -syntax

````
NTSTATUS WdfRequestRetrieveUnsafeUserInputBuffer(
  _In_      WDFREQUEST Request,
  _In_      size_t     MinimumRequiredLength,
  _Out_     PVOID      *InputBuffer,
  _Out_opt_ size_t     *Length
);
````


## -parameters

### -param Request [in]

A handle to a framework request object. 


### -param MinimumRequiredLength [in]

The minimum buffer size, in bytes, that the driver needs to process the I/O request.


### -param InputBuffer [out]

A pointer to a location that receives the buffer's address.


### -param Length [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>WdfRequestRetrieveUnsafeUserInputBuffer</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>This value is returned if one of the following occurs:

The method was not called from within the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function.

The I/O request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>.

The request specifies <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> or <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a>.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The <i>MinimumRequiredLength</i> parameter specifies a buffer size that is larger than the buffer's actual size.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.


## -remarks
The <b>WdfRequestRetrieveUnsafeUserInputBuffer</b> method must be called from an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function. After calling <b>WdfRequestRetrieveUnsafeUserInputBuffer</b>, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforread.md">WdfRequestProbeAndLockUserBufferForRead</a>. 

The driver can call <b>WdfRequestRetrieveUnsafeUserInputBuffer</b> if a request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

For more information about <b>WdfRequestRetrieveUnsafeUserInputBuffer</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

For a code example that uses <b>WdfRequestRetrieveUnsafeUserInputBuffer</b>, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforread.md">WdfRequestProbeAndLockUserBufferForRead</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforread.md">WdfRequestProbeAndLockUserBufferForRead</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveunsafeuseroutputbuffer.md">WdfRequestRetrieveUnsafeUserOutputBuffer</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestRetrieveUnsafeUserInputBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

