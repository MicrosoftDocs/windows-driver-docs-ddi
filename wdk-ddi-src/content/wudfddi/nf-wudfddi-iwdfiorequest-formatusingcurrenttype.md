---
UID: NF:wudfddi.IWDFIoRequest.FormatUsingCurrentType
title: IWDFIoRequest::FormatUsingCurrentType method
author: windows-driver-content
description: The FormatUsingCurrentType method formats an I/O request so that the driver can forward it, unmodified, to the next-lower driver.
old-location: wdf\iwdfiorequest_formatusingcurrenttype.htm
old-project: wdf
ms.assetid: 4cbf6d29-bccd-4629-b282-eb5314f9b4f4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfiorequest_formatusingcurrenttype, IWDFIoRequest, IWDFIoRequest interface, FormatUsingCurrentType method, FormatUsingCurrentType method, IWDFIoRequest interface, wudfddi/IWDFIoRequest::FormatUsingCurrentType, UMDFRequestObjectRef_e16e60fe-557d-413c-a483-6bbe602986dc.xml, FormatUsingCurrentType, IWDFIoRequest::FormatUsingCurrentType, FormatUsingCurrentType method, umdf.iwdfiorequest_formatusingcurrenttype
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
-	IWDFIoRequest.FormatUsingCurrentType
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::FormatUsingCurrentType method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatUsingCurrentType</b> method formats an I/O request so that the driver can forward it, unmodified, to the next-lower driver.


## -syntax


````
void  FormatUsingCurrentType();
````


## -parameters





## -returns


None



## -remarks


When a driver receives an I/O request, the driver might forward the request to the local I/O target, unmodified. To forward the unmodified request, the driver must:
<ul>
<li>
Call <b>FormatUsingCurrentType</b> to format the request so that the framework can pass the request to the driver's local I/O target.

</li>
<li>
Call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method to send the request to the I/O target.

</li>
</ul>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::FormatUsingCurrentType method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

