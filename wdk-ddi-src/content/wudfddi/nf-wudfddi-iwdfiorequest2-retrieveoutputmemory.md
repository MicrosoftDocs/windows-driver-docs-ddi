---
UID: NF:wudfddi.IWDFIoRequest2.RetrieveOutputMemory
title: IWDFIoRequest2::RetrieveOutputMemory (wudfddi.h)
description: The RetrieveOutputMemory method retrieves the IWDFMemory interface of a framework memory object that represents an I/O request's output buffer.
old-location: wdf\iwdfiorequest2_retrieveoutputmemory.htm
tech.root: wdf
ms.assetid: d17e7435-adc3-4248-a6c9-c7e267504291
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest2 interface,RetrieveOutputMemory method, IWDFIoRequest2.RetrieveOutputMemory, IWDFIoRequest2::RetrieveOutputMemory, RetrieveOutputMemory, RetrieveOutputMemory method, RetrieveOutputMemory method,IWDFIoRequest2 interface, UMDFRequestObjectRef_9fbbb5ad-480f-4744-805a-1af1dd841274.xml, umdf.iwdfiorequest2_retrieveoutputmemory, wdf.iwdfiorequest2_retrieveoutputmemory, wudfddi/IWDFIoRequest2::RetrieveOutputMemory
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoRequest2.RetrieveOutputMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::RetrieveOutputMemory


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveOutputMemory</b> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's output buffer.


## -parameters




### -param Memory [out]

The address of a location that receives a pointer to the <b>IWDFMemory</b> interface of a UMDF memory object.


## -returns



<b>RetrieveOutputMemory</b> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT_BUFFER)</b></dt>
</dl>
</td>
<td width="60%">
The I/O request did not provide an input buffer.

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



A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <b>RetrieveOutputMemory</b> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <b>RetrieveOutputMemory</b> method retrieves the output buffer for I/O requests that use the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> method for accessing data buffers.

If <b>RetrieveOutputMemory</b> returns S_OK, the driver receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a UMDF memory object that represents the output buffer. To access the buffer, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a>. 

The driver can access the retrieved framework memory object until it <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a> the I/O request. Before the driver completes the I/O request, it must call <b>IWDFMemory::Release</b>. 

Instead of calling <b>RetrieveOutputMemory</b>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>, which retrieves the buffer's address and length.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556875">IQueueCallbackRead::OnRead</a> callback function can obtain the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of the framework memory object that represents a read request's output buffer. The example then formats and sends the read request to a USB I/O target. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
  CMyQueue::OnRead(
     __in IWDFIoQueue *pWdfQueue,
     __in IWDFIoRequest *pWdfRequest,
     __in SIZE_T BytesToRead
     )
{
    HRESULT hr = S_OK;
    IWDFMemory * pOutputMemory = NULL;

    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr&lt;IWDFIoRequest2> r2 = pWdfRequest;

    r2->RetrieveOutputMemory(&pOutputMemory);
    if (FAILED(hr)) goto Exit;

    hr = m_Device->GetInputPipe()->FormatRequestForRead(pWdfRequest,
                                                        NULL,
                                                        pOutputMemory,
                                                        NULL,
                                                        NULL);
Exit:
    if (FAILED(hr))
    {
        pWdfRequest->Complete(hr);
    }
    else
    {
        ForwardFormattedRequest(pWdfRequest, m_Device->GetInputPipe());
    }
    SAFE_RELEASE(pOutputMemory);
    return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559037">IWDFIoRequest2::RetrieveInputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>
 

 

