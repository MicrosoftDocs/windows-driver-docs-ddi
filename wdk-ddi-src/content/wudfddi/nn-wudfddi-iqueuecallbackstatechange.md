---
UID: NN:wudfddi.IQueueCallbackStateChange
title: IQueueCallbackStateChange
author: windows-driver-content
description: An I/O queue object raises an event when it changes state. A driver can consume the event by registering the IQueueCallbackStateChange interface.
old-location: wdf\iqueuecallbackstatechange.htm
old-project: wdf
ms.assetid: 39c66462-015d-49ba-9a37-0b3b928e5fbf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iqueuecallbackstatechange, IQueueCallbackStateChange interface, IQueueCallbackStateChange interface, described, IQueueCallbackStateChange, wudfddi/IQueueCallbackStateChange, UMDFQueueObjectRef_57a57868-6a9d-42b3-8c74-ceb6c4be03c3.xml, umdf.iqueuecallbackstatechange
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wudfddi.h
apiname:
-	IQueueCallbackStateChange
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IQueueCallbackStateChange interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue object raises an event when it changes state. A driver can consume the event by registering the <b>IQueueCallbackStateChange</b> interface.


## -members

The <b>IQueueCallbackStateChange</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556880">IQueueCallbackStateChange::OnStateChange</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/69a422a1-b878-496e-b1b9-e04b7c3db121">OnStateChange</a> method is called when the state of the I/O queue object changes. 

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/69a422a1-b878-496e-b1b9-e04b7c3db121">OnStateChange</a> method is called when the state of the I/O queue object changes. 

 


## -remarks


A driver registers the <b>IQueueCallbackStateChange</b> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. 


