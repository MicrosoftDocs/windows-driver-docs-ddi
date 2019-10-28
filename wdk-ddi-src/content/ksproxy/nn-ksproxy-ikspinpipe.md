---
UID: NN:ksproxy.IKsPinPipe
title: IKsPinPipe (ksproxy.h)
description: The IKsPinPipe interface is for proxy use and not recommended for application use. IKsPinPipe provides methods that control a pin pipe.
old-location: stream\ikspinpipe.htm
tech.root: stream
ms.assetid: bb9ebe0b-4a6e-41ff-a460-6c0b3a749d8d
ms.date: 04/23/2018
ms.keywords: IKsPinPipe, IKsPinPipe interface [Streaming Media Devices], IKsPinPipe interface [Streaming Media Devices],described, ksproxy/IKsPinPipe, ksproxy_baf35b14-3ad8-491c-86cf-9ac2b76d9504.xml, stream.ikspinpipe
ms.topic: interface
f1_keywords:
 - "ksproxy/IKsPinPipe"
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsPinPipe
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPinPipe interface


## -description


The <b>IKsPinPipe</b> interface is for proxy use and not recommended for application use. <b>IKsPinPipe</b> provides methods that control a pin pipe. 

The IID for this interface is IID_IKsPinPipe.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsPinPipe</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsPinPipe</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-ksgetconnectedpin">KsGetConnectedPin</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-ksgetfiltername">KsGetFilterName</a>
</td>
<td align="left" width="63%">
Returns the name of a filter

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-ksgetpinbuscache">KsGetPinBusCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-ksgetpinframingcache">KsGetPinFramingCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-ksgetpinname">KsGetPinName</a>
</td>
<td align="left" width="63%">
Returns the name of a pin. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-ksgetpipe">KsGetPipe</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-ksgetpipeallocatorflag">KsGetPipeAllocatorFlag</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-kssetpinbuscache">KsSetPinBusCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-kssetpinframingcache">KsSetPinFramingCache</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-kssetpipe">KsSetPipe</a>
</td>
<td align="left" width="63%">
Not recommended for application use.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspinpipe-kssetpipeallocatorflag">KsSetPipeAllocatorFlag</a>
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

