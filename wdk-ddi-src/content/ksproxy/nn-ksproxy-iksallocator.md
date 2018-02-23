---
UID: NN:ksproxy.IKsAllocator
title: IKsAllocator
author: windows-driver-content
description: TheIKsAllocator interface provides methods that control and query an allocator. IKsAllocator is for proxy use and not recommended for application use.
old-location: stream\iksallocator.htm
old-project: stream
ms.assetid: 0d6db041-e5ea-4394-9d88-b4b5b377fe1d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.iksallocator, IKsAllocator interface [Streaming Media Devices], IKsAllocator interface [Streaming Media Devices], described, IKsAllocator, ksproxy/IKsAllocator, ksproxy_f3288ae8-cea3-4892-9b5b-f03e2c5ec8c4.xml
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
-	Ksproxy.lib
-	Ksproxy.dll
apiname:
-	IKsAllocator
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsAllocator interface


## -description


The<b>IKsAllocator</b> interface provides methods that control and query an allocator.  <b>IKsAllocator</b>  is for proxy use and not recommended for application use.  


## -members

The <b>IKsAllocator</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/9F79816F-866F-4B68-898F-87D310EFBBE7">KsGetAllocatorHandle</a>
</td>
<td align="left" width="63%">
Retrieves a file handle to an allocator.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/47B51B6F-555A-4A1E-AA25-7E94DC0060CC">KsGetAllocatorMode</a>
</td>
<td align="left" width="63%">
Returns the mode in which an allocator allocates memory.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/139F4465-1228-4603-B92F-4CB73E1A6DC0">KsGetAllocatorStatus</a>
</td>
<td align="left" width="63%">
Retrieves the status of an allocator.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/8F64E58D-9C04-43BA-9C1B-88AD081176A9">KsSetAllocatorMode</a>
</td>
<td align="left" width="63%">
Sets the mode in which an allocator allocates memory.

</td>
</tr>
</table>Retrieves a file handle to an allocator.

Returns the mode in which an allocator allocates memory.

Retrieves the status of an allocator.

Sets the mode in which an allocator allocates memory.

 


## -remarks



The IID for this interface is IID_IKsAllocator.



