---
UID: NN:ksproxy.IKsPinPipe
title: IKsPinPipe
author: windows-driver-content
description: The IKsPinPipe interface is for proxy use and not recommended for application use. IKsPinPipe provides methods that control a pin pipe.
old-location: stream\ikspinpipe.htm
old-project: stream
ms.assetid: bb9ebe0b-4a6e-41ff-a460-6c0b3a749d8d
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPinPipe, IKsPinPipe interface [Streaming Media Devices], IKsPinPipe interface [Streaming Media Devices], described, ksproxy/IKsPinPipe, ksproxy_baf35b14-3ad8-491c-86cf-9ac2b76d9504.xml, stream.ikspinpipe
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsPinPipe
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsPinPipe interface


## -description


The <b>IKsPinPipe</b> interface is for proxy use and not recommended for application use. <b>IKsPinPipe</b> provides methods that control a pin pipe. 

The IID for this interface is IID_IKsPinPipe.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPinPipe</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsPinPipe</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsPinPipe</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/9025E49D-A12B-4617-9441-13B61137853E">KsGetConnectedPin</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/A009B276-AF91-4FDD-AB81-6992311B3744">KsGetFilterName</a>
</td>
<td align="left" width="63%">
Returns the name of a filter

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/4F38C7D7-E350-4FCB-A89B-CA87BA638AD3">KsGetPinBusCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/981596AB-0E39-49B3-8586-B2D9C2762D80">KsGetPinFramingCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2757FF0D-C84E-4309-AFD4-D9FE1F4D77CE">KsGetPinName</a>
</td>
<td align="left" width="63%">
Returns the name of a pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/5672C7E2-83AA-4BDC-BE60-E2BC54BD636F">KsGetPipe</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/EBF5B615-A7B1-4B44-855C-7956334AAF75">KsGetPipeAllocatorFlag</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/5340DB05-12D9-4965-B207-BA113F3801A7">KsSetPinBusCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/E334FEE1-DD78-4906-ADFA-1B496F91BA28">KsSetPinFramingCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/FAA97E98-FB31-462E-9776-5C27A10FD773">KsSetPipe</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0587E952-8B51-44C3-8E23-2981C00ADB43">KsSetPipeAllocatorFlag</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

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

