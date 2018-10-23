---
UID: NN:ksproxy.IKsPin
title: IKsPin
author: windows-driver-content
description: The IKsPin interface provides methods that control and retrieve information about a pin.
old-location: stream\ikspin.htm
tech.root: stream
ms.assetid: 4717300c-bc98-4e1f-83c3-cbd368b45140
ms.date: 04/23/2018
ms.keywords: IKsPin, IKsPin interface [Streaming Media Devices], IKsPin interface [Streaming Media Devices],described, ksproxy/IKsPin, ksproxy_9a020f8a-1271-47ea-816f-1132e44b6f45.xml, stream.ikspin
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsPin
-	IKsPin.KsReceiveAllocator
-	IKsPin.KsRenegotiateAllocator
-	IKsPin.KsQualityNotify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPin interface


## -description


The <b>IKsPin</b> interface provides methods that control and retrieve information about a pin.

The IID for this interface is IID_IKsPin.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPin</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsPin</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsPin</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/68faba0a-8057-4259-b93d-c19899637356">KsCreateSinkPinHandle</a>
</td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Creates a pin handle and stores it in the KS pin object. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/92e0355c-b89f-46c2-b406-e3c73fc37000">KsDecrementPendingIoCount</a>
</td>
<td align="left" width="63%">
Decrements the number of I/O operations that are in progress on a pin.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e527a659-7ed5-4262-bed2-3bab58919401">KsDeliver</a>
</td>
<td align="left" width="63%">
Delivers a media sample from an output pin to an input pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/3fca9bf5-5430-4877-846e-e796e54991a2">KsGetCurrentCommunication</a>
</td>
<td align="left" width="63%">
Retrieves the current communication direction, interface, and medium of a pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e79ae2ac-6636-491d-8c98-70a5ff3a23ef">KsIncrementPendingIoCount</a>
</td>
<td align="left" width="63%">
Increments the number of I/O operations that are in progress on a pin.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/df3bbc09-14aa-4243-887b-d88d02a59f73">KsMediaSamplesCompleted</a>
</td>
<td align="left" width="63%">
Informs a pin that a stream segment completed. Used by interface handlers.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/fd833d0b-2f81-4002-8280-38e17e528af6">KsPeekAllocator</a>
</td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Returns a pointer to a <b>IMemAllocator</b> interface for a pin's assigned allocator.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/059bef5a-1db7-4fd7-a19b-c34df81f4447">KsPropagateAcquire</a>
</td>
<td align="left" width="63%">
For proxy use and not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>KsQualityNotify</b></td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Receives quality-management reports from the kernel-mode equivalent of a DirectShow pin.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/e8b0a1c0-c018-4556-b43c-fae4f7cf43de">KsQueryInterfaces</a>
</td>
<td align="left" width="63%">
Retrieves interfaces that a pin supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/de6efd10-7f97-422a-abd4-c21c4cbc1dd7">KsQueryMediums</a>
</td>
<td align="left" width="63%">
Retrieves mediums that a pin supports.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>KsReceiveAllocator</b></td>
<td align="left" width="63%">
For proxy use and not recommended for application use. Provides an allocator for an output pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>KsRenegotiateAllocator</b></td>
<td align="left" width="63%">
Obsolete. Do not use.

</td>
</tr>
</table> 


## -remarks



An interface handler (<a href="https://msdn.microsoft.com/library/windows/hardware/ff559855">IKsInterfaceHandler</a>) uses many of the <b>IKsPin</b> methods to route media samples of a particular media type. 
    




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559855">IKsInterfaceHandler</a>
 

 

