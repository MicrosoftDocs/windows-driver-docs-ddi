---
UID: NN:ksproxy.IKsClockPropertySet
title: IKsClockPropertySet (ksproxy.h)
description: The IKsClockPropertySet interface provides methods that let the proxy accurately reflect time.
old-location: stream\iksclockpropertyset.htm
tech.root: stream
ms.assetid: bf50d4b1-782f-4d15-b6ef-23fa13da68ff
ms.date: 04/23/2018
ms.keywords: IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], IKsClockPropertySet interface [Streaming Media Devices],described, ksproxy/IKsClockPropertySet, ksproxy_0be3eb82-08b7-4afc-a4e5-3815f7499ad0.xml, stream.iksclockpropertyset
ms.topic: interface
f1_keywords:
 - "ksproxy/IKsClockPropertySet"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Ksproxy.lib
- Ksproxy.dll
api_name:
- IKsClockPropertySet
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsClockPropertySet interface


## -description


The <b>IKsClockPropertySet</b> interface provides methods that let the proxy accurately reflect time.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsClockPropertySet</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IKsClockPropertySet</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsClockPropertySet</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetcorrelatedphysicaltime">KsGetCorrelatedPhysicalTime</a>
</td>
<td align="left" width="63%">
Retrieves the physical time and the correlated system time from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetcorrelatedtime">KsGetCorrelatedTime</a>
</td>
<td align="left" width="63%">
Retrieves the presentation time and the correlated system time from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetphysicaltime">KsGetPhysicalTime</a>
</td>
<td align="left" width="63%">
Retrieves the current physical time from the underlying clock. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetresolution">KsGetResolution</a>
</td>
<td align="left" width="63%">
Retrieves the clock resolution from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetstate">KsGetState</a>
</td>
<td align="left" width="63%">
Retrieves the streaming state of a pin from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgettime">KsGetTime</a>
</td>
<td align="left" width="63%">
Retrieves the current presentation time from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-kssetcorrelatedphysicaltime">KsSetCorrelatedPhysicalTime</a>
</td>
<td align="left" width="63%">
Sets the physical time with the correlated system time on the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-kssetcorrelatedtime">KsSetCorrelatedTime</a>
</td>
<td align="left" width="63%">
Sets the correlated system time with the presentation time on the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-kssetphysicaltime">KsSetPhysicalTime</a>
</td>
<td align="left" width="63%">
Sets the current physical time on the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-kssettime">KsSetTime</a>
</td>
<td align="left" width="63%">
Sets the current presentation time on the underlying clock.

</td>
</tr>
</table> 


## -remarks



The IID for this interface is IID_IKsClockPropertySet.



