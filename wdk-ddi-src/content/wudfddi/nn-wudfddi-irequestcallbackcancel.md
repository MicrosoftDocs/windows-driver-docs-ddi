---
UID: NN:wudfddi.IRequestCallbackCancel
title: IRequestCallbackCancel
author: windows-driver-content
description: A driver is notified when an I/O request that the driver is currently processing is to be canceled.
old-location: wdf\irequestcallbackcancel.htm
tech.root: wdf
ms.assetid: d6aec38c-6cbb-494c-9fa4-10b6f4a30ae0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IRequestCallbackCancel, IRequestCallbackCancel interface, IRequestCallbackCancel interface,described, UMDFRequestObjectRef_6f54b76d-812d-437c-8c02-7d9e3e177b90.xml, umdf.irequestcallbackcancel, wdf.irequestcallbackcancel, wudfddi/IRequestCallbackCancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
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
-	wudfddi.h
api_name:
-	IRequestCallbackCancel
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRequestCallbackCancel interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver is notified when an I/O request that the driver is currently processing is to be canceled. The driver is notified when an application calls the Microsoft Win32 <b>CancelIo</b>, <b>CancelIoEx</b>, or <b>CancelSynchronousIo</b> function. The driver can handle the notification by registering the <b>IRequestCallbackCancel</b> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IRequestCallbackCancel</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IRequestCallbackCancel</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IRequestCallbackCancel</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/67c85eaa-bb47-4384-8e37-fdbbc879b352">OnCancel</a> method is called when an application cancels an I/O operation through the Microsoft Win32 <b>CancelIo</b>, <b>CancelIoEx</b>, or <b>CancelSynchronousIo</b> function. 

</td>
</tr>
</table> 


## -remarks



A driver registers the <b>IRequestCallbackCancel</b> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> method to enable the canceling of an I/O request. For more information about how to cancel I/O requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.



