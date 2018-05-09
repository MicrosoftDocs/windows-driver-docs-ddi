---
UID: NF:wudfddi.IQueueCallbackCreate.OnCreateFile
title: IQueueCallbackCreate::OnCreateFile
author: windows-driver-content
description: The OnCreateFile method is called to handle an open file request when an application opens a device through the Microsoft Win32 CreateFile function.
old-location: wdf\iqueuecallbackcreate_oncreatefile.htm
old-project: wdf
ms.assetid: f569d306-4e1e-44b7-acb0-6b46abc26b37
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IQueueCallbackCreate interface,OnCreateFile method, IQueueCallbackCreate.OnCreateFile, IQueueCallbackCreate::OnCreateFile, OnCreateFile, OnCreateFile method, OnCreateFile method,IQueueCallbackCreate interface, UMDFQueueObjectRef_db0b57a0-6086-4e2a-87bd-71e5a1e4f46d.xml, umdf.iqueuecallbackcreate_oncreatefile, wdf.iqueuecallbackcreate_oncreatefile, wudfddi/IQueueCallbackCreate::OnCreateFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IQueueCallbackCreate.OnCreateFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackCreate::OnCreateFile


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCreateFile</b> method is called to handle an open file request when an application opens a device through the Microsoft Win32 <b>CreateFile</b> function. 


## -parameters




### -param pWdfQueue [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a> interface for the I/O queue object that the request arrives from. 


### -param pWDFRequest




### -param pWdfFileObject [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface for the file object that is associated with the device. This information is provided for convenience because the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559088">IWDFIoRequest::GetCreateParameters</a> method to obtain the file object. 


#### - pWdfRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface that represents the framework request object. 


## -returns



None




## -remarks



If the driver implements the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556837">IQueueCallbackCreate</a> interface, the framework calls the <b>OnCreateFile</b> method when an application opens a device through the Win32 <b>CreateFile</b> function to perform an I/O operation, such as reading from or writing to a file. 

A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556837">IQueueCallbackCreate</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue.

A typical <b>OnCreateFile</b> method might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560208">IWDFObject::AssignContext</a> method on the file object to associate context with the file object, and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> to complete the request.

A UMDF driver might be required to open registry keys or files while it impersonates a client that sends the I/O requests. From its implementation of the <b>OnCreateFile</b> method, the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a> method to set a security impersonation level and to set the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a> method in which the driver handles the impersonation. To access necessary resources by using the credentials of the user, the framework calls the driver's <b>OnImpersonate</b> method. For any operations other than those that require impersonation, the framework calls driver methods that run under the default driver account. For more information about how UMDF and UMDF drivers handle impersonation, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Impersonation</a>.


#### Examples

This example is based on the WpdWudfSampleDriver sample, and is from the Queue.cpp file.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>STDMETHODIMP_ (void) CQueue::OnCreateFile(
/*[in]*/ IWDFIoQueue* pQueue,
/*[in]*/ IWDFIoRequest* pRequest,
/*[in]*/ IWDFFile* pFileObject
)
{
HRESULT hr = S_OK;
ClientContext* pClientContext = new ClientContext ();
. . . //Code omitted.
if(pClientContext != NULL) {
hr = pFileObject-&gt;AssignContext (this, (void*)pClientContext);
// Release the client context if we cannot set it
if(FAILED(hr)) {
pClientContext-&gt;Release();
pClientContext = NULL;
}
}
else {
hr = E_OUTOFMEMORY;
}
pRequest-&gt;Complete(hr);
return;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556837">IQueueCallbackCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559088">IWDFIoRequest::GetCreateParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a>
 

 

