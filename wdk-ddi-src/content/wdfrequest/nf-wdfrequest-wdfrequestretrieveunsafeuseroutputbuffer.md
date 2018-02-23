---
UID: NF:wdfrequest.WdfRequestRetrieveUnsafeUserOutputBuffer
title: WdfRequestRetrieveUnsafeUserOutputBuffer function
author: windows-driver-content
description: The WdfRequestRetrieveUnsafeUserOutputBuffer method retrieves an I/O request's output buffer, if the request's technique for accessing data buffers is neither buffered nor direct I/O.
old-location: wdf\wdfrequestretrieveunsafeuseroutputbuffer.htm
old-project: wdf
ms.assetid: 7969f683-3426-4863-8afe-d9cbe490a4b5
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: kmdf.wdfrequestretrieveunsafeuseroutputbuffer, wdfrequest/WdfRequestRetrieveUnsafeUserOutputBuffer, DFRequestObjectRef_3f483887-e2fa-413d-b147-9f18fc092800.xml, WdfRequestRetrieveUnsafeUserOutputBuffer, WdfRequestRetrieveUnsafeUserOutputBuffer method, wdf.wdfrequestretrieveunsafeuseroutputbuffer
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
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedReadA, BufAfterReqCompletedWrite, DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, OutputBufferAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfRequestRetrieveUnsafeUserOutputBuffer
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestRetrieveUnsafeUserOutputBuffer function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestRetrieveUnsafeUserOutputBuffer</b> method retrieves an I/O request's output buffer, if the request's technique for accessing data buffers is <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>.


## -syntax


````
NTSTATUS WdfRequestRetrieveUnsafeUserOutputBuffer(
  _In_      WDFREQUEST Request,
  _In_      size_t     MinimumRequiredLength,
  _Out_     PVOID      *OutputBuffer,
  _Out_opt_ size_t     *Length
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


### -param MinimumRequiredLength [in]

The minimum buffer size, in bytes, that the driver needs to process the I/O request.


### -param OutputBuffer [out]

A pointer to a location that receives the buffer's address.


### -param Length [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>WdfRequestRetrieveUnsafeUserOutputBuffer</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The method was not called from within the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function.

</li>
<li>
The I/O request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>.

</li>
<li>
The request specifies <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> or <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a>.

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
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <b>WdfRequestRetrieveUnsafeUserOutputBuffer</b> method must be called from an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a> callback function. After calling <b>WdfRequestRetrieveUnsafeUserOutputBuffer</b>, the driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforwrite.md">WdfRequestProbeAndLockUserBufferForWrite</a>. 

The driver can call <b>WdfRequestRetrieveUnsafeUserOutputBuffer</b> if a request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

For more information about <b>WdfRequestRetrieveUnsafeUserOutputBuffer</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfRequestRetrieveUnsafeUserOutputBuffer</b>, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforread.md">WdfRequestProbeAndLockUserBufferForRead</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveunsafeuserinputbuffer.md">WdfRequestRetrieveUnsafeUserInputBuffer</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforwrite.md">WdfRequestProbeAndLockUserBufferForWrite</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_io_in_caller_context.md">EvtIoInCallerContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestRetrieveUnsafeUserOutputBuffer method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

