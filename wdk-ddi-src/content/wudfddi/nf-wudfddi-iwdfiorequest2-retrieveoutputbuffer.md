---
UID: NF:wudfddi.IWDFIoRequest2.RetrieveOutputBuffer
title: IWDFIoRequest2::RetrieveOutputBuffer method
author: windows-driver-content
description: The RequestRetrieveOutputBuffer method retrieves an I/O request's output buffer.
old-location: wdf\iwdfiorequest2_retrieveoutputbuffer.htm
old-project: wdf
ms.assetid: c2c96663-df1b-4310-b51e-177e353bb059
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest2, IWDFIoRequest2 interface, RetrieveOutputBuffer method, IWDFIoRequest2::RetrieveOutputBuffer, RetrieveOutputBuffer method, RetrieveOutputBuffer method, IWDFIoRequest2 interface, RetrieveOutputBuffer,IWDFIoRequest2.RetrieveOutputBuffer, UMDFRequestObjectRef_895f34da-95f3-4256-a049-0221887da5e1.xml, umdf.iwdfiorequest2_retrieveoutputbuffer, wdf.iwdfiorequest2_retrieveoutputbuffer, wudfddi/IWDFIoRequest2::RetrieveOutputBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest2.RetrieveOutputBuffer
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest2::RetrieveOutputBuffer method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.


## -parameters




### -param MinimumRequiredCb [in]

The minimum buffer size, in bytes, that the driver needs to process the I/O request. This value can be zero if there is no minimum buffer size.


### -param Buffer [out]

A pointer to a location that receives the buffer's address.


### -param BufferCb [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns




<a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:

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



A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> method retrieves the output buffer for I/O requests that use the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> method for accessing data buffers.

If <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> returns S_OK, the driver receives the address and, optionally, the size of the output buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a> the I/O request.

Instead of calling <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

The following code example shows a segment of a serial port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556854">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a> callback function. The code segment obtains the I/O request's output buffer and then transfers baud rate information from the device to the buffer.

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
    CComQIPtr&lt;IWDFIoRequest2&gt; r2 = pWdfRequest;

    switch (ControlCode)
    {
        case IOCTL_SERIAL_GET_BAUD_RATE:
        {
            SERIAL_BAUD_RATE *pBaudRateBuffer;
            hr = pWdfRequest2-&gt;RetrieveOutputBuffer(sizeof(SERIAL_BAUD_RATE),
                                                    (PVOID*) &amp;pBaudRateBuffer,
                                                    NULL);
            if (SUCCEEDED(hr))
                  {
                      RtlZeroMemory(pBaudRateBuffer, sizeof(SERIAL_BAUD_RATE));
                      pBaudRateBuffer-&gt;BaudRate = m_Device-&gt;GetBaudRate();
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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559037">IWDFIoRequest2::RetrieveInputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>
 

 

