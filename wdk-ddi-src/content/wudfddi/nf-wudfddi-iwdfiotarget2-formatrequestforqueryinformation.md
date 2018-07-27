---
UID: NF:wudfddi.IWDFIoTarget2.FormatRequestForQueryInformation
title: IWDFIoTarget2::FormatRequestForQueryInformation
author: windows-driver-content
description: The FormatRequestForQueryInformation method formats an I/O request to obtain information about a file, but it does not send the request to an I/O target.
old-location: wdf\iwdfiotarget2_formatrequestforqueryinformation.htm
tech.root: wdf
ms.assetid: 24ce2918-1d9f-41eb-add1-a50b888f0a99
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FormatRequestForQueryInformation, FormatRequestForQueryInformation method, FormatRequestForQueryInformation method,IWDFIoTarget2 interface, IWDFIoTarget2 interface,FormatRequestForQueryInformation method, IWDFIoTarget2.FormatRequestForQueryInformation, IWDFIoTarget2::FormatRequestForQueryInformation, UMDFIoTargetObjectRef_8057f7bc-65c3-491b-9aa3-a5fc9e790524.xml, umdf.iwdfiotarget2_formatrequestforqueryinformation, wdf.iwdfiotarget2_formatrequestforqueryinformation, wudfddi/IWDFIoTarget2::FormatRequestForQueryInformation
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
-	IWDFIoTarget2.FormatRequestForQueryInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget2::FormatRequestForQueryInformation


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForQueryInformation</b> method formats an I/O request to obtain information about a file, but it does not send the request to an I/O target.


## -parameters




### -param pRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface of the request object that represents the I/O request. 


### -param InformationClass [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561405">WDF_FILE_INFORMATION_CLASS</a>-typed value that specifies the type of information to obtain.


### -param pFile [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface of the file object that is associated with the I/O request. This parameter is required for local and remote <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">I/O targets</a>, and is optional (can be <b>NULL</b>) for file handle I/O targets.


### -param pInformationMemory [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a memory object. This object represents the output buffer, which receives the file information that the <i>InformationClass</i> parameter specifies. This parameter is optional and can be <b>NULL</b>.


### -param pInformationMemoryOffset [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the output buffer, for the data transfer. If this pointer is <b>NULL</b>, the data transfer begins at the beginning of the output buffer, and the transfer size is the buffer size.


## -returns



<b>FormatRequestForQueryInformation</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:

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



Use the <b>FormatRequestForQueryInformation</b> method, followed by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method, to send requests either synchronously or asynchronously to an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">I/O target</a>. 


#### Examples

The following code example is part of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. If the callback function receives a query information request, it sends the request to the device's default I/O target.

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
    IWDFMemory *pOutMemory;
    WDF_FILE_INFORMATION_CLASS infoClass;

    //
    // Obtain the device, default I/O target, and file object.
    //
    pQueue-&gt;GetDevice(&amp;pDevice);
    pDevice-&gt;GetDefaultIoTarget(&amp;pTarget);
    pRequest-&gt;GetFileObject(&amp;pFile);

    if (WdfRequestQueryInformation==pRequest-&gt;GetType())
    {
        //
        // Declare an IWDFIoRequest2 interface pointer and obtain the
        // IWDFIoRequest2 interface from the IWDFIoRequest interface.
        //
        CComQIPtr&lt;IWDFIoRequest2&gt; r2 = pRequest;

        // 
        // Declare an IWDFIoTarget2 interface pointer and obtain the
        // IWDFIoTarget2 interface from the IWDFIoTarget interface.
        //
        CComQIPtr&lt;IWDFIoTarget2&gt; target2(pTarget);

        // 
        // Get the I/O request's output buffer.
        // 
        hr = pWdfRequest2-&gt;RetrieveOutputMemory(&amp;pOutMemory);
        if (!SUCCEEDED(hr)) goto Error;

        // 
        // Get the I/O request's parameters.
        // 
        hr = pWdfRequest2-&gt;GetQueryInformationParameters(&amp;infoClass,
                                                         NULL);
        if (!SUCCEEDED(hr)) goto Error;

        //
        // Format a query information request and send it to the I/O target.
        //
        hr = target2-&gt;FormatRequestForQueryInformation(pRequest,
                                                       infoClass,
                                                       pFile,
                                                       pOutMemory,
                                                       NULL);
        if (!SUCCEEDED(hr)) goto Error;
        hr = pRequest-&gt;Send(pTarget,
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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559191">IWDFIoTarget2::FormatRequestForSetInformation</a>
 

 

