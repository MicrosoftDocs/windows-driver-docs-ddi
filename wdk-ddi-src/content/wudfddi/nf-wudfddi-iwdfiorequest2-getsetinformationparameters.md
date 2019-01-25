---
UID: NF:wudfddi.IWDFIoRequest2.GetSetInformationParameters
title: IWDFIoRequest2::GetSetInformationParameters (wudfddi.h)
description: The GetSetInformationParameters method retrieves parameters that are associated with a WdfRequestSetInformation-typed I/O request.
old-location: wdf\iwdfiorequest2_getsetinformationparameters.htm
tech.root: wdf
ms.assetid: 44872d92-4a71-4cc7-9f7c-c95477ac3264
ms.date: 02/26/2018
ms.keywords: GetSetInformationParameters, GetSetInformationParameters method, GetSetInformationParameters method,IWDFIoRequest2 interface, IWDFIoRequest2 interface,GetSetInformationParameters method, IWDFIoRequest2.GetSetInformationParameters, IWDFIoRequest2::GetSetInformationParameters, UMDFRequestObjectRef_ed4dd211-1a7c-4ca3-9450-ab4320ece88d.xml, umdf.iwdfiorequest2_getsetinformationparameters, wdf.iwdfiorequest2_getsetinformationparameters, wudfddi/IWDFIoRequest2::GetSetInformationParameters
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
-	IWDFIoRequest2.GetSetInformationParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2::GetSetInformationParameters


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetSetInformationParameters</b> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a>-typed I/O request.


## -parameters




### -param pInformationClass [out, optional]

A pointer to a driver-allocated variable that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561405">WDF_FILE_INFORMATION_CLASS</a>-typed value. This pointer is optional and can be <b>NULL</b>.


### -param pSizeInBytes [out, optional]

A pointer to a driver-allocated variable that receives the size, in bytes, of the file information. This pointer is optional and can be <b>NULL</b>.


## -returns



None.




## -remarks



Your driver can call <b>GetSetInformationParameters</b> to obtain the parameters that are associated with an I/O request, if the request type is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a>. The <i>pInformationClass</i> parameter identifies the type of file information that the driver should set, and the <i>pSizeInBytes</i> parameter specifies the size of the buffer that contains the information. The driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a> to obtain the buffer address. 

Your driver must verify that the specified buffer size is large enough to contain the file information that the driver must set.


#### Examples

The following code example is part of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. If the callback function receives a set information request, it retrieves the request's parameters. If the driver supports the specified type of information, it copies the information from the request's input buffer.

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
    WDF_FILE_INFORMATION_CLASS infoClass;
    SIZE_T bufSize;
    PFILE_BASIC_INFORMATION buffer;

 if (WdfRequestQueryInformation==pRequest-&gt;GetType())
    {
        //
        // Declare an IWDFIoRequest2 interface pointer and obtain the
        // IWDFIoRequest2 interface from the IWDFIoRequest interface.
        //
        CComQIPtr&lt;IWDFIoRequest2&gt; r2 = pRequest;
        // 
        // Get the I/O request's parameters.
        // 
        r2-&gt;GetSetInformationParameters(&amp;infoClass,
                                        &amp;bufSize);
        // 
        // This driver supports only FileBasicInformation.
        // 
        if (infoClass != FileBasicInformation)
        {
            hr = HRESULT_FROM_NT(STATUS_NOT_SUPPORTED);
            goto exit;
        }
        // 
        // Validate buffer size.
        // 
        if (bufferCb != sizeof(FILE_BASIC_INFORMATION))
        {
            hr = HRESULT_FROM_NT(STATUS_BUFFER_TOO_SMALL);
            goto exit;
        }
        // 
        // Get input buffer.
        // 
 hr = r2-&gt;RetrieveInputBuffer(sizeof(FILE_BASIC_INFORMATION), 
                              (PVOID*) &amp;buffer,
                              &amp;bufferCb);
 if (SUCCEEDED(hr))
        {
            // 
            // Copy file information from input buffer.
            // 
            CopyMemory(&amp;g_FileInfo,
                       buffer,
                       sizeof(FILE_BASIC_INFORMATION));
        }
 ...
    }
...
exit:
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558997">IWDFIoRequest2::GetQueryInformationParameters</a>
 

 

