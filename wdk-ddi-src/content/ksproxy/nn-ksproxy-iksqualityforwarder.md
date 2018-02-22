---
UID: NN:ksproxy.IKsQualityForwarder
title: IKsQualityForwarder
author: windows-driver-content
description: The IKsQualityForwarder interface inherits the method of the IKsObject interface and extends IKsObject to provide a method that flushes information from a pin.
old-location: stream\iksqualityforwarder.htm
old-project: stream
ms.assetid: 1f0ebadc-4a6c-4d57-ba96-936ce138142b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.iksqualityforwarder, IKsQualityForwarder interface [Streaming Media Devices], IKsQualityForwarder interface [Streaming Media Devices], described, IKsQualityForwarder, ksproxy/IKsQualityForwarder, ksproxy_ed147fca-8a84-407c-861a-f33625d90bc7.xml
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
-	ksproxy.h
apiname:
-	IKsQualityForwarder
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsQualityForwarder interface


## -description


The <b>IKsQualityForwarder</b> interface inherits the method of the <a href="..\ksproxy\nn-ksproxy-iksobject.md">IKsObject</a> interface and extends <b>IKsObject</b> to provide a method that flushes information from a pin. 


## -members

The <b>IKsQualityForwarder</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0a1b5094-4abd-4d57-8d8c-b385fb0d46de">KsFlushClient</a>
</td>
<td align="left" width="63%">
Flushes information from a pin. 

</td>
</tr>
</table>Flushes information from a pin. 

 


## -remarks



The IID for this interface is IID_IKsQualityForwarder.



