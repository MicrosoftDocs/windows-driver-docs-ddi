---
UID: NN:ksproxy.IKsObject
title: IKsObject (ksproxy.h)
description: The IKsObject interface provides a method to retrieve the file handle of a KS object.
old-location: stream\iksobject.htm
tech.root: stream
ms.assetid: c4422564-3fc0-4087-b628-056488c723e6
ms.date: 04/23/2018
ms.keywords: IKsObject, IKsObject interface [Streaming Media Devices], IKsObject interface [Streaming Media Devices],described, ksproxy_6432effa-13f1-4b39-a158-c315a93108d4.xml, stream.iksobject
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
req.lib: Ksproxy.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
-	ksproxy.h.dll
api_name:
-	IKsObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsObject interface


## -description


The <b>IKsObject</b> interface provides a method to retrieve the file handle of a KS object. 


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsObject</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsObject</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsObject</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/55c4f362-eb3c-4c4f-a048-7abdd270f67f">KsGetObjectHandle</a>
</td>
<td align="left" width="63%">
Retrieves the file handle of a KS object.

</td>
</tr>
</table> 


## -remarks



The IID for this interface is IID_IKsObject.

<b>IKsObject</b> is defined in <i>Ksproxy.h</i> within the #ifdef __STREAMS__ section.

__STREAMS__ is defined in <i>Stream.h</i>, a header from the DirectX SDK.



