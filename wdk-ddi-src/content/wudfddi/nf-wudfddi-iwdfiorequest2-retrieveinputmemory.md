---
UID: NF:wudfddi.IWDFIoRequest2.RetrieveInputMemory
title: IWDFIoRequest2::RetrieveInputMemory method
author: windows-driver-content
description: The RetrieveInputMemory method retrieves the IWDFMemory interface of a framework memory object that represents an I/O request's input buffer.
old-location: wdf\iwdfiorequest2_retrieveinputmemory.htm
old-project: wdf
ms.assetid: 32596330-6cd9-4f82-9140-7f9a26cf7932
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RetrieveInputMemory method, IWDFIoRequest2, IWDFIoRequest2::RetrieveInputMemory, RetrieveInputMemory method, IWDFIoRequest2 interface, RetrieveInputMemory, wudfddi/IWDFIoRequest2::RetrieveInputMemory, UMDFRequestObjectRef_48cb0129-5727-4321-a4c5-77ae12fd685b.xml, IWDFIoRequest2 interface, RetrieveInputMemory method, wdf.iwdfiorequest2_retrieveinputmemory, umdf.iwdfiorequest2_retrieveinputmemory
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequest2.RetrieveInputMemory
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoRequest2::RetrieveInputMemory method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveInputMemory</b> method retrieves the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface of a framework memory object that represents an I/O request's input buffer.


## -syntax


````
HRESULT RetrieveInputMemory(
  [out] IWDFMemory **Memory
);
````


## -parameters




### -param Memory [out]

The address of a location that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface of a UMDF memory object.


## -returns



<b>RetrieveInputMemory</b> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:

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
The I/O request did not provide an output buffer.

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



A request's input buffer contains information, such as data to be written to a disk, that the originator of the request supplied. Your driver can call <b>RetrieveInputMemory</b> to obtain the input buffer for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).

The <b>RetrieveInputMemory</b> method retrieves the input buffer for I/O requests that use the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> method for accessing data buffers. 

If <b>RetrieveInputMemory</b> returns S_OK, the driver receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface of a UMDF memory object that represents the input buffer. To access the buffer, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a>.

The driver can access the retrieved framework memory object until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a> the I/O request. Before the driver completes the I/O request, it must call <b>IWDFMemory::Release</b>. 

Instead of calling <b>RetrieveInputMemory</b>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>, which retrieves the buffer's address and length.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556885">IQueueCallbackWrite::OnWrite</a> callback function can obtain the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface of the framework memory object that represents a write request's input buffer. The example then formats and sends the write request to a USB I/O target. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
  CMyQueue::OnWrite(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in SIZE_T BytesToWrite
    )
{
    HRESULT hr = S_OK;
    IWDFMemory * pInputMemory = NULL;
    IWDFUsbTargetPipe * pOutputPipe = m_Device-&gt;GetOutputPipe();
    //
    // Declare an IWDFIoRequest2 interface pointer and obtain the
    // IWDFIoRequest2 interface from the IWDFIoRequest interface.
    //
    CComQIPtr&lt;IWDFIoRequest2&gt; r2 = pWdfRequest;

    hr = r2-&gt;RetrieveInputMemory(&amp;pInputMemory);
    if (FAILED(hr)) goto Exit;

    hr = pOutputPipe-&gt;FormatRequestForWrite(
                                           pWdfRequest,
                                           NULL, //pFile
                                           pInputMemory,
                                           NULL, //Memory offset
                                           NULL  //DeviceOffset
                                           );
Exit:
    if (FAILED(hr))
    {
        pWdfRequest-&gt;Complete(hr);
    }
    else
    {
        ForwardFormattedRequest(pWdfRequest, pOutputPipe);
    }
    SAFE_RELEASE(pInputMemory);
 return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::RetrieveInputMemory method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

