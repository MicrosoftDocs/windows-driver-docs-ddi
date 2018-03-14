---
UID: NF:wudfddi.IWDFIoRequest3.RetrieveActivityId
title: IWDFIoRequest3::RetrieveActivityId method
author: windows-driver-content
description: The RetrieveActivityId method retrieves the current activity identifier associated with an I/O request.
old-location: wdf\iwdfiorequest3_retrieveactivityid.htm
old-project: wdf
ms.assetid: A90FCF3C-B648-4E97-887E-FCE58D7FA13A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest3, IWDFIoRequest3 interface, RetrieveActivityId method, IWDFIoRequest3::RetrieveActivityId, RetrieveActivityId method, RetrieveActivityId method, IWDFIoRequest3 interface, RetrieveActivityId,IWDFIoRequest3.RetrieveActivityId, umdf.iwdfiorequest3_retrieveactivityid, wdf.iwdfiorequest3_retrieveactivityid, wudfddi/IWDFIoRequest3::RetrieveActivityId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	IWDFIoRequest3.RetrieveActivityId
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest3::RetrieveActivityId method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The 
  <b>RetrieveActivityId</b> method retrieves the current activity identifier associated with an I/O request.


## -syntax


````
HRESULT RetrieveActivityId(
  [out] LPGUID ActivityId
);
````


## -parameters




### -param ActivityId [out]

A pointer to a location to store the retrieved GUID.


## -returns



<b>RetrieveActivityId</b> returns returns S_OK if the call is successful. Otherwise, this method might return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32   (ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
No activity ID is associated with the request.

</td>
</tr>
</table>
 




## -remarks



Requests reflected from kernel mode have an activity identifier available only if the Kernel Trace provider is enabled or if the UMDF driver called <a href="https://msdn.microsoft.com/57CB3CED-FE46-4A74-9E23-82640B7EF1DC">IWDFIoRequest3::SetActivityId</a> after receiving the request. For more information about Event Tracing for Windows (ETW), see <a href="https://msdn.microsoft.com/3de69436-671b-46a2-8d92-4eb3af2a4233">Event Tracing</a>.

Requests initiated by the UMDF driver have an activity identifier available only if the UMDF driver previously called  <a href="https://msdn.microsoft.com/57CB3CED-FE46-4A74-9E23-82640B7EF1DC">IWDFIoRequest3::SetActivityId</a>.

The framework does not clear a request's activity identifier when the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559048">IWdfIoRequest2::Reuse</a>.

For more information about activity identifiers, see <a href="https://msdn.microsoft.com/2B70953F-5192-4654-9506-6A84373D20B4">Using Activity Identifiers</a>.

The UMDF 2 equivalent of this method is <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveactivityid.md">WdfRequestRetrieveActivityId</a>.


#### Examples

The following code example shows a driver can retrieve an  activity identifier from one request and then use it to set the activity identifier for another request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>hrQI = pWdfRequest-&gt;QueryInterface(IID_PPV_ARGS(&amp;pOriginalRequest3));
ASSERT(SUCCEEDED(hrQI));

hrQI = pNewRequest-&gt;QueryInterface(IID_PPV_ARGS(&amp;pNewRequest3));
ASSERT(SUCCEEDED(hrQI));

//
// Obtain activity id from original request and set in the new one
//

pOriginalRequest3-&gt;RetrieveActivityId(&amp;activityId);
pNewRequest3-&gt;SetActivityId(&amp;activityId);

pOriginalRequest3-&gt;Release();
pNewRequest3-&gt;Release();

</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest3.md">IWDFIoRequest3</a>



<a href="https://msdn.microsoft.com/57CB3CED-FE46-4A74-9E23-82640B7EF1DC">IWDFIoRequest3::SetActivityId</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest3::RetrieveActivityId method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

