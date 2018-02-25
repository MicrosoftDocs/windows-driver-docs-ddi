---
UID: NN:ksproxy.IKsNotifyEvent
title: IKsNotifyEvent
author: windows-driver-content
description: The IKsNotifyEvent interface provides a method to cause the KS object that owns a DirectShow event to issue the event with the given parameters.
old-location: stream\iksnotifyevent.htm
old-project: stream
ms.assetid: 1de4db64-be4c-4a9b-b1ab-29f703e17959
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IKsNotifyEvent, IKsNotifyEvent interface [Streaming Media Devices], IKsNotifyEvent interface [Streaming Media Devices], described, ksproxy/IKsNotifyEvent, ksproxy_1ef13fd1-5ccb-410c-8b0e-4942d9ba790e.xml, stream.iksnotifyevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Ksproxy.lib
-	Ksproxy.dll
apiname:
-	IKsNotifyEvent
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsNotifyEvent interface


## -description


<b>DirectX 9.0 and later versions only.</b>

The <b>IKsNotifyEvent</b> interface provides a method to cause the KS object that owns a DirectShow event to issue the event with the given parameters.

The IID for this interface is IID_IKsNotifyEvent


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsNotifyEvent</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsNotifyEvent</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsNotifyEvent</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c0813b1a-402e-46ba-8d81-e31cdcbbb8dd">KsNotifyEvent</a>
</td>
<td align="left" width="63%">
Sets up for notification whenever action related to a DirectShow event occurs.

</td>
</tr>
</table> 

