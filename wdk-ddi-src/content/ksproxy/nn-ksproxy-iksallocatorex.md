---
UID: NN:ksproxy.IKsAllocatorEx
title: IKsAllocatorEx
author: windows-driver-content
description: The IKsAllocatorEx interface is for proxy use and not recommended for application use. IKsAllocatorEx inherits all the methods of the IKsAllocator interface and extends IKsAllocator to provide methods that further control and query an allocator.
old-location: stream\iksallocatorex.htm
old-project: stream
ms.assetid: 42abaf2b-8ee9-450e-aef3-fa29d1b558e5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: stream.iksallocatorex, IKsAllocatorEx interface [Streaming Media Devices], IKsAllocatorEx interface [Streaming Media Devices], described, IKsAllocatorEx, ksproxy/IKsAllocatorEx, ksproxy_58c9c83a-1a11-4e08-bf7f-e0694bf2eda5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
-	IKsAllocatorEx
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsAllocatorEx interface


## -description


The <b>IKsAllocatorEx</b> interface is for proxy use and not recommended for application use. <b>IKsAllocatorEx</b> inherits all the methods of the <b>IKsAllocator</b> interface and extends <b>IKsAllocator</b> to provide methods that further control and query an allocator. 

The IID for this interface is IID_IKsAllocatorEx.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsAllocatorEx</b> interface inherits from IUnknown and <a href="..\ksproxy\nn-ksproxy-iksallocator.md">IKsAllocator</a>. <b>IKsAllocatorEx</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsAllocatorEx</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/82F2FE7D-D02B-47A1-8FC7-2D5CFC4CADA1">KsGetProperties</a>
</td>
<td align="left" width="63%">
Returns the properties for an allocator.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/E259B3D0-7536-4287-A7A2-367407D97F33">KsSetAllocatorHandle</a>
</td>
<td align="left" width="63%">
Sets the handle for an allocator.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/17145801-5EE4-4022-997A-03B14C794D2F">KsSetProperties</a>
</td>
<td align="left" width="63%">
Sets the properties for an allocator. 

</td>
</tr>
</table> 
<h3><a id="methods"></a><a id="METHODS"></a>Inherited Methods</h3>The following methods are listed in Vtable order.
<table>
<tr>
<th>IUnknown method</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>QueryInterface</b>

</td>
<td>
Returns pointers to supported interfaces.

</td>
</tr>
<tr>
<td>
<b>AddRef</b>

</td>
<td>
Increments reference count.

</td>
</tr>
<tr>
<td>
<b>Release</b>

</td>
<td>
Decrements reference count.

</td>
</tr>
</table> 
<table>
<tr>
<th>IKsAllocator method</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>KsGetAllocatorHandle</b>

</td>
<td>
Retrieves a file handle to an allocator.

</td>
</tr>
<tr>
<td>
<b>KsGetAllocatorMode</b>

</td>
<td>
Returns the mode in which an allocator allocates memory.

</td>
</tr>
<tr>
<td>
<b>KsGetAllocatorStatus</b>

</td>
<td>
Retrieves the status of an allocator.

</td>
</tr>
<tr>
<td>
<b>KsSetAllocatorMode</b>

</td>
<td>
Sets the mode in which an allocator allocates memory.

</td>
</tr>
</table> 


## -see-also

<a href="..\ksproxy\nn-ksproxy-iksallocator.md">IKsAllocator</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsAllocatorEx interface%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

