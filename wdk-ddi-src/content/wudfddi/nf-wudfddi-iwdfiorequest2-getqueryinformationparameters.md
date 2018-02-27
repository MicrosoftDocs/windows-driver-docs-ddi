---
UID: NF:wudfddi.IWDFIoRequest2.GetQueryInformationParameters
title: IWDFIoRequest2::GetQueryInformationParameters method
author: windows-driver-content
description: The GetQueryInformationParameters method retrieves parameters that are associated with a WdfRequestQueryInformation-typed I/O request.
old-location: wdf\iwdfiorequest2_getqueryinformationparameters.htm
old-project: wdf
ms.assetid: e189d2f6-ef1c-45ed-8b55-8aae0661a426
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: GetQueryInformationParameters method, GetQueryInformationParameters method, IWDFIoRequest2 interface, GetQueryInformationParameters,IWDFIoRequest2.GetQueryInformationParameters, IWDFIoRequest2, IWDFIoRequest2 interface, GetQueryInformationParameters method, IWDFIoRequest2::GetQueryInformationParameters, UMDFRequestObjectRef_595d2b4c-1286-4243-b440-0efaae03980d.xml, umdf.iwdfiorequest2_getqueryinformationparameters, wdf.iwdfiorequest2_getqueryinformationparameters, wudfddi/IWDFIoRequest2::GetQueryInformationParameters
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest2.GetQueryInformationParameters
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest2::GetQueryInformationParameters method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetQueryInformationParameters</b> method retrieves parameters that are associated with a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WdfRequestQueryInformation</a>-typed I/O request.


## -syntax


````
void GetQueryInformationParameters(
  [out, optional] WDF_FILE_INFORMATION_CLASS *pInformationClass,
  [out, optional] SIZE_T                     *pSizeInBytes
);
````


## -parameters




### -param pInformationClass [out, optional]

A pointer to a driver-allocated variable that receives a <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_file_information_class.md">WDF_FILE_INFORMATION_CLASS</a>-typed value. This pointer is optional and can be <b>NULL</b>.


### -param pSizeInBytes [out, optional]

A pointer to a driver-allocated variable that receives the size, in bytes, of the file information. This pointer is optional and can be <b>NULL</b>.


## -returns



None.




## -remarks



Your driver can call <b>GetQueryInformationParameters</b> to obtain the parameters that are associated with an I/O request, if the request type is <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WdfRequestQueryInformation</a>. The <i>pInformationClass</i> parameter identifies the type of file information that the driver should provide, and the <i>pSizeInBytes</i> parameter specifies the size of the buffer that will receive the information. The driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a> to obtain the buffer address. 

Your driver must verify that the specified buffer size is large enough to receive the requested file information.


#### Examples

The following code example is part of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a> callback function. If the callback function receives a query information request, it retrieves the request's parameters. If the driver supports the specified type of information, it copies the information into the request's output buffer.

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
        r2-&gt;GetQueryInformationParameters(&amp;infoClass,
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
        // Get output buffer.
        // 
        hr = r2-&gt;RetrieveOutputBuffer(sizeof(FILE_BASIC_INFORMATION), 
                                      (PVOID*) &amp;buffer,
                                      &amp;bufferCb);
        if (SUCCEEDED(hr))
        {
            // 
            // Copy file information to output buffer.
            // 
            CopyMemory(buffer,
                       &amp;g_FileInfo,
                       sizeof(FILE_BASIC_INFORMATION));
            r2-&gt;SetInformation(sizeof(FILE_BASIC_INFORMATION));
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

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559009">IWDFIoRequest2::GetSetInformationParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::GetQueryInformationParameters method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

