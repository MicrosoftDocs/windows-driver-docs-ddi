---
UID: NF:wudfddi.IWDFIoRequest.GetFileObject
title: IWDFIoRequest::GetFileObject
author: windows-driver-content
description: The GetFileObject method retrieves a pointer to the IWDFFile interface that is associated with an I/O request.
old-location: wdf\iwdfiorequest_getfileobject.htm
tech.root: wdf
ms.assetid: 2d6567f1-9e2a-405f-ae8d-eb531cc29275
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetFileObject, GetFileObject method, GetFileObject method,IWDFIoRequest interface, IWDFIoRequest interface,GetFileObject method, IWDFIoRequest.GetFileObject, IWDFIoRequest::GetFileObject, UMDFRequestObjectRef_50a8506d-039a-448a-8459-30e89ac1021c.xml, umdf.iwdfiorequest_getfileobject, wdf.iwdfiorequest_getfileobject, wudfddi/IWDFIoRequest::GetFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
-	IWDFIoRequest.GetFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest::GetFileObject


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetFileObject</b> method retrieves a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface that is associated with an I/O request.


## -parameters




### -param ppFileObject [out]

A pointer to a buffer that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface for the file object. Note that returning <b>NULL</b> is valid.


## -returns



None




## -remarks



When your driver calls <b>GetFileObject</b>, the framework increments the reference count on the interface.  Your driver is responsible for releasing the reference when finished with the interface pointer. To do so, either use a smart pointer that automatically decrements the reference count when the object goes out of context, or call  <a href="https://msdn.microsoft.com/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a">Release</a> on the interface when finished with it.


#### Examples

The following code example is taken from the WpdMultiTransportDriver sample in the WDK. The example declares a smart pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface, calls <b>GetFileObject</b>, and then calls <a href="https://msdn.microsoft.com/b76acae1-3c37-4095-bf8b-1785dc90f378">RetrieveContext</a> on the file object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>  CComPtr&lt;IWDFFile&gt;   pFileObject;

  ...

  // Get the Context map for this client

  pRequest-&gt;GetFileObject(&amp;pFileObject);

  if (pFileObject != NULL)
  {
      hr = pFileObject-&gt;RetrieveContext((void**)&amp;pClientContextMap);
      CHECK_HR(hr, "Failed to get Contextmap from WDF File Object");
  }
  </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>
 

 

