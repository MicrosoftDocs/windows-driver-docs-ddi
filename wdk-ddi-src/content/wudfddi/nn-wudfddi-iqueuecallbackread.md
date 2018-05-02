---
UID: NN:wudfddi.IQueueCallbackRead
title: IQueueCallbackRead
author: windows-driver-content
description: An I/O queue notifies a driver when a read request is available for the driver.
old-location: wdf\iqueuecallbackread.htm
old-project: wdf
ms.assetid: ccae49a2-2081-44f2-b1f6-cb1e98b74e5d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IQueueCallbackRead, IQueueCallbackRead interface, IQueueCallbackRead interface,described, UMDFQueueObjectRef_ea1187c2-6bd1-43a0-aeeb-6d9e1ee48cd7.xml, umdf.iqueuecallbackread, wdf.iqueuecallbackread, wudfddi/IQueueCallbackRead
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
-	IQueueCallbackRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# IQueueCallbackRead interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue notifies a driver when a read request is available for the driver. The I/O queue notifies the driver when an application calls the Microsoft Win32 <b>ReadFile</b> or <b>ReadFileEx</b> function. The driver can handle the notification by registering the <b>IQueueCallbackRead</b> interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackRead</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IQueueCallbackRead</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IQueueCallbackRead</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556875">IQueueCallbackRead::OnRead</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/e11a823d-0b08-42fd-b093-4c464c152afe">OnRead</a> method is called to handle a read request when an application reads information from a device through the Microsoft Win32 <b>ReadFile</b> or <b>ReadFileEx</b> function. 

</td>
</tr>
</table> 


## -remarks



A driver registers the <b>IQueueCallbackRead</b> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. For more information about creating or configuring an I/O queue, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">Configuring Dispatch Mode for an I/O Queue</a>.



