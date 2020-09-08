---
UID: NF:wudfddi.IWDFIoRequest2.RetrieveInputBuffer
title: IWDFIoRequest2::RetrieveInputBuffer (wudfddi.h)
description: The RequestRetrieveInputBuffer method retrieves an I/O request's input buffer.
old-location: wdf\iwdfiorequest2_retrieveinputbuffer.htm
tech.root: wdf
ms.assetid: f727d9b7-d7ea-4551-bc5a-7829f9807e02
ms.date: 02/26/2018
keywords: ["IWDFIoRequest2::RetrieveInputBuffer"]
ms.keywords: IWDFIoRequest2 interface,RetrieveInputBuffer method, IWDFIoRequest2.RetrieveInputBuffer, IWDFIoRequest2::RetrieveInputBuffer, RetrieveInputBuffer, RetrieveInputBuffer method, RetrieveInputBuffer method,IWDFIoRequest2 interface, UMDFRequestObjectRef_d4e2aa27-329a-4438-8010-579f8a3a3363.xml, umdf.iwdfiorequest2_retrieveinputbuffer, wdf.iwdfiorequest2_retrieveinputbuffer, wudfddi/IWDFIoRequest2::RetrieveInputBuffer
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFIoRequest2::RetrieveInputBuffer
 - wudfddi/IWDFIoRequest2::RetrieveInputBuffer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest2.RetrieveInputBuffer
---

# IWDFIoRequest2::RetrieveInputBuffer


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> method retrieves an I/O request's input buffer.

## -parameters

### -param MinimumRequiredCb 

[in]
The minimum buffer size, in bytes, that the driver needs to process the I/O request. This value can be zero if there is no minimum buffer size.

### -param Buffer 

[out]
A pointer to a location that receives the buffer's address.

### -param BufferCb 

[out, optional]
A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.

## -returns

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</b></dt>
</dl>
</td>
<td width="60%">
The I/O request did not provide an input buffer, or the size of the input buffer is less than the minimum size that <i>MinimumRequiredCb</i> specifies.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Not enough memory is available to retrieve the buffer. The driver should complete the request with an error status value.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.

## -remarks

A request's input buffer contains information, such as data to be written to a disk, that the originator of the request supplied. Your driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> to obtain the input buffer for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> method retrieves the input buffer for I/O requests that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> method for accessing data buffers.

If <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> returns S_OK, the driver receives the address and, optionally, the size of the input buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a> the I/O request.

Instead of calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveinputmemory">IWDFIoRequest2::RetrieveInputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

The following code example shows a segment of a serial port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackdeviceiocontrol-ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a> callback function. From an I/O request's input buffer, the code segment obtains the baud rate that should be set for the device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
  CMyQueue::OnDeviceIoControl(
    __in IWDFIoQueue*  FxQueue,
    __in IWDFIoRequest*  FxRequest,
    __in ULONG  ControlCode,
    __in SIZE_T  InputBufferCb,
    __in SIZE_T  OutputBufferCb
    )
{
    PBYTE buffer;
    SIZE_T bufferSize;
    HRESULT hr;
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr<IWDFIoRequest2> r2 = FxRequest;

    switch (ControlCode)
    {
        case IOCTL_SERIAL_SET_BAUD_RATE: 
        {
            //
            // Obtain the baud rate from the write request's input buffer.
            //
            hr = r2->RetrieveInputBuffer(sizeof(SERIAL_BAUD_RATE),
                                         (PVOID*) &buffer, 
                                         &bufferSize);
...
        }
    }
}</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveinputmemory">IWDFIoRequest2::RetrieveInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveoutputbuffer">IWDFIoRequest2::RetrieveOutputBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveoutputmemory">IWDFIoRequest2::RetrieveOutputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFIoRequest::GetInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>

