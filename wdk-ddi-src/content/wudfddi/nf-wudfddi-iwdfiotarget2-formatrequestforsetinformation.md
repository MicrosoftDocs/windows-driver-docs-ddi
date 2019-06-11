---
UID: NF:wudfddi.IWDFIoTarget2.FormatRequestForSetInformation
title: IWDFIoTarget2::FormatRequestForSetInformation (wudfddi.h)
description: The FormatRequestForSetInformation method formats an I/O request to set information about a file, but it does not send the request to an I/O target.
old-location: wdf\iwdfiotarget2_formatrequestforsetinformation.htm
tech.root: wdf
ms.assetid: 2bfdc5c6-da5a-43c1-9165-02d6c448a690
ms.date: 02/26/2018
ms.keywords: FormatRequestForSetInformation, FormatRequestForSetInformation method, FormatRequestForSetInformation method,IWDFIoTarget2 interface, IWDFIoTarget2 interface,FormatRequestForSetInformation method, IWDFIoTarget2.FormatRequestForSetInformation, IWDFIoTarget2::FormatRequestForSetInformation, UMDFIoTargetObjectRef_234ebe5b-1d13-47e5-873d-feb45b12c850.xml, umdf.iwdfiotarget2_formatrequestforsetinformation, wdf.iwdfiotarget2_formatrequestforsetinformation, wudfddi/IWDFIoTarget2::FormatRequestForSetInformation
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
- IWDFIoTarget2.FormatRequestForSetInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget2::FormatRequestForSetInformation


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForSetInformation</b> method formats an I/O request to set information about a file, but it does not send the request to an I/O target.


## -parameters




### -param pRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface of the request object that represents the I/O request. 


### -param InformationClass [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561405">WDF_FILE_INFORMATION_CLASS</a>-typed value that specifies the type of information to set.


### -param pFile [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface of the file object that is associated with the I/O request. This parameter is required for local and remote <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">I/O targets</a>, and is optional (can be <b>NULL</b>) for file handle I/O targets.


### -param pInformationMemory [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a memory object. This object represents the input buffer, which contains driver-supplied file information that the <i>InformationClass</i> parameter specifies. This parameter is optional and can be <b>NULL</b>.


### -param pInformationMemoryOffset [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the input buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the input buffer, and the transfer size is the buffer size.


## -returns



<b>FormatRequestForSetInformation</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework was unable to allocate memory.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.




## -remarks



Use the <b>FormatRequestForSetInformation</b> method, followed by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method, to send requests either synchronously or asynchronously to an <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">I/O target</a>. 


#### Examples

The following code example is part of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. If the callback function receives a set information request, it sends the request to the device's default I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void
CMyQueue::OnDefaultIoHandler(
 IWDFIoQueue*  pQueue,
 IWDFIoRequest*  pRequest
    )
{
    HRESULT hr;
    IWDFDevice *pDevice;
    IWDFIoTarget *pTarget;
    IWDFFile *pFile;
    IWDFMemory *pInMemory;
    WDF_FILE_INFORMATION_CLASS infoClass;

    //
    // Obtain the device, default I/O target, and file object.
    //
    pQueue->GetDevice(&pDevice);
    pDevice->GetDefaultIoTarget(&pTarget);
    pRequest->GetFileObject(&pFile);

    if (WdfRequestQueryInformation==pRequest->GetType())
    {
        //
        // Declare an IWDFIoRequest2 interface pointer and obtain the
        // IWDFIoRequest2 interface from the IWDFIoRequest interface.
        //
        CComQIPtr<IWDFIoRequest2> r2 = pRequest;

        // 
        // Declare an IWDFIoTarget2 interface pointer and obtain the
        // IWDFIoTarget2 interface from the IWDFIoTarget interface.
        //
        CComQIPtr<IWDFIoTarget2> target2(pTarget);

        // 
        // Get the I/O request's input buffer.
        // 
        hr = pWdfRequest2->RetrieveInputMemory(&pInMemory);
        if (!SUCCEEDED(hr)) goto Error;

        // 
        // Get the I/O request's parameters.
        // 
        hr = pWdfRequest2->GetSetInformationParameters(&infoClass,
                                                       NULL);
        if (!SUCCEEDED(hr)) goto Error;

        //
        // Format a query information request and send it to the I/O target.
        //
        hr = target2->FormatRequestForSetInformation(pRequest,
                                                     infoClass,
                                                     pFile,
                                                     pInMemory,
                                                     NULL);
        if (!SUCCEEDED(hr)) goto Error;
        hr = pRequest->Send(pTarget,
                            WDF_REQUEST_SEND_OPTION_SYNCHRONOUS,
                            0);
    }
...
Error;
    //
    // Release objects.
    //
    SAFE_RELEASE(pDevice);
    SAFE_RELEASE(pTarget);
    SAFE_RELEASE(pFile);
    SAFE_RELEASE(pOutMemory);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559175">IWDFIoTarget2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559184">IWDFIoTarget2::FormatRequestForQueryInformation</a>
 

 

