---
UID: NF:wudfddi.IWDFIoRequest.GetIoQueue
title: IWDFIoRequest::GetIoQueue method
author: windows-driver-content
description: The GetIoQueue method retrieves the I/O queue object that is associated with an I/O request.
old-location: wdf\iwdfiorequest_getioqueue.htm
old-project: wdf
ms.assetid: 834d5ee3-b28b-4d75-b0b7-be1f36ace8aa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetIoQueue method, GetIoQueue method, IWDFIoRequest interface, GetIoQueue,IWDFIoRequest.GetIoQueue, IWDFIoRequest, IWDFIoRequest interface, GetIoQueue method, IWDFIoRequest::GetIoQueue, UMDFRequestObjectRef_1e603d95-06ae-45a8-ab4d-3592d6e140bf.xml, umdf.iwdfiorequest_getioqueue, wdf.iwdfiorequest_getioqueue, wudfddi/IWDFIoRequest::GetIoQueue
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest.GetIoQueue
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::GetIoQueue method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetIoQueue</b> method retrieves the I/O queue object that is associated with an I/O request.


## -syntax


````
void GetIoQueue(
  [out] IWDFIoQueue **ppWdfIoQueue
);
````


## -parameters




### -param ppWdfIoQueue [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue object that the I/O request is associated with.


## -returns



None




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::GetIoQueue method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

