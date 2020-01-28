---
UID: NF:wudfddi.IWDFIoRequest2.RetrieveOutputBuffer
title: IWDFIoRequest2::RetrieveOutputBuffer (wudfddi.h)
description: The RequestRetrieveOutputBuffer method retrieves an I/O request's output buffer.
old-location: wdf\iwdfiorequest2_retrieveoutputbuffer.htm
tech.root: wdf
ms.assetid: c2c96663-df1b-4310-b51e-177e353bb059
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest2 interface,RetrieveOutputBuffer method, IWDFIoRequest2.RetrieveOutputBuffer, IWDFIoRequest2::RetrieveOutputBuffer, RetrieveOutputBuffer, RetrieveOutputBuffer method, RetrieveOutputBuffer method,IWDFIoRequest2 interface, UMDFRequestObjectRef_895f34da-95f3-4256-a049-0221887da5e1.xml, umdf.iwdfiorequest2_retrieveoutputbuffer, wdf.iwdfiorequest2_retrieveoutputbuffer, wudfddi/IWDFIoRequest2::RetrieveOutputBuffer
f1_keywords:
 - "wudfddi/IWDFIoRequest2.RetrieveOutputBuffer"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoRequest2.RetrieveOutputBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::RetrieveOutputBuffer


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.


## -parameters




### -param MinimumRequiredCb [in]

The minimum buffer size, in bytes, that the driver needs to process the I/O request. This value can be zero if there is no minimum buffer size.


### -param Buffer [out]

A pointer to a location that receives the buffer's address.


### -param BufferCb [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">RequestRetrieveOutputBuffer</a> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:

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
The I/O request did not provide an output buffer, or the size of the output buffer is less than the minimum size that <i>MinimumRequiredCb</i> specifies.

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



A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">RequestRetrieveOutputBuffer</a> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">RequestRetrieveOutputBuffer</a> method retrieves the output buffer for I/O requests that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> method for accessing data buffers.

If <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">RequestRetrieveOutputBuffer</a> returns S_OK, the driver receives the address and, optionally, the size of the output buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a> the I/O request.

Instead of calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">RequestRetrieveOutputBuffer</a>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveoutputmemory">IWDFIoRequest2::RetrieveOutputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

The following code example shows a segment of a serial port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackdeviceiocontrol-ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a> callback function. The code segment obtains the I/O request's output buffer and then transfers baud rate information from the device to the buffer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
  CMyQueue::OnDeviceIoControl(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in ULONG ControlCode,
    __in SIZE_T InputBufferSizeInBytes,
    __in SIZE_T OutputBufferSizeInBytes
    )
{
    HRESULT hr;
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr<IWDFIoRequest2> r2 = pWdfRequest;

    switch (ControlCode)
    {
        case IOCTL_SERIAL_GET_BAUD_RATE:
        {
            SERIAL_BAUD_RATE *pBaudRateBuffer;
            hr = pWdfRequest2->RetrieveOutputBuffer(sizeof(SERIAL_BAUD_RATE),
                                                    (PVOID*) &pBaudRateBuffer,
                                                    NULL);
            if (SUCCEEDED(hr))
                  {
                      RtlZeroMemory(pBaudRateBuffer, sizeof(SERIAL_BAUD_RATE));
                      pBaudRateBuffer->BaudRate = m_Device->GetBaudRate();
                      reqCompletionInfo = sizeof(SERIAL_BAUD_RATE);
                  }
            
        }
        break;
        ...
    }
    ...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveinputbuffer">IWDFIoRequest2::RetrieveInputBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveinputmemory">IWDFIoRequest2::RetrieveInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveoutputmemory">IWDFIoRequest2::RetrieveOutputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getinputmemory">IWDFIoRequest::GetInputMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getoutputmemory">IWDFIoRequest::GetOutputMemory</a>
 

 

