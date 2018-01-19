---
UID: NF:wdfrequest.WdfRequestRetrieveInputBuffer
title: WdfRequestRetrieveInputBuffer function
author: windows-driver-content
description: The WdfRequestRetrieveInputBuffer method retrieves an I/O request's input buffer.
old-location: wdf\wdfrequestretrieveinputbuffer.htm
old-project: wdf
ms.assetid: fa02a787-502c-48a3-a5e1-710d7513c42e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfRequestRetrieveInputBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestRetrieveInputBuffer
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedWrite, BufAfterReqCompletedWriteA, DriverCreate, InputBufferAPI, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestRetrieveInputBuffer function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestRetrieveInputBuffer</b> method retrieves an I/O request's input buffer.



## -syntax

````
NTSTATUS WdfRequestRetrieveInputBuffer(
  _In_      WDFREQUEST Request,
  _In_      size_t     MinimumRequiredSize,
  _Out_     PVOID      *Buffer,
  _Out_opt_ size_t     *Length
);
````


## -parameters

### -param Request [in]

A handle to a framework request object. 


### -param MinimumRequiredSize [in]

The minimum buffer size, in bytes, that the driver needs to process the I/O request.


### -param Buffer [out]

A pointer to a location that receives the buffer's address.


### -param Length [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns
<b>WdfRequestRetrieveInputBuffer</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The input buffer's length is zero, or the <i>MinimumRequiredSize</i> parameter specifies a buffer size that is larger than the buffer's actual size.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The request type is not valid or the request is using <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. For more information about supported methods for accessing data buffers, see the following Remarks section.
<dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl>The request has already been completed.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There is insufficient memory.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.


## -remarks
A request's input buffer contains information, such as data to be written to a disk, that was supplied by the originator of the request. Your driver can call <b>WdfRequestRetrieveInputBuffer</b> to obtain the input buffer for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).

The <b>WdfRequestRetrieveInputBuffer</b> method retrieves the input buffer for I/O requests that use the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> method or the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveInputBuffer</b> also supports I/O requests that use <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. 

If <b>WdfRequestRetrieveInputBuffer</b> returns STATUS_SUCCESS, the driver receives the address and, optionally, the size of the input buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

Instead of calling <b>WdfRequestRetrieveInputBuffer</b>, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about <b>WdfRequestRetrieveInputBuffer</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

The following code example is part of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Serial</a> sample driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a> callback function. If the I/O control code is IOCTL_SERIAL_SET_TIMEOUT, the driver obtains new time-out values from the I/O request's input buffer.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputmemory.md">WdfRequestRetrieveInputMemory</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">WdfRequestRetrieveOutputBuffer</a>
</dt>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceretrieveconfigdescriptor.md">WdfUsbTargetDeviceRetrieveConfigDescriptor</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestRetrieveInputBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

