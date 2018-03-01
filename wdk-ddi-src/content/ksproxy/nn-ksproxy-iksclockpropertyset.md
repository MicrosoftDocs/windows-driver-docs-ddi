---
UID: NN:ksproxy.IKsClockPropertySet
title: IKsClockPropertySet
author: windows-driver-content
description: The IKsClockPropertySet interface provides methods that let the proxy accurately reflect time.
old-location: stream\iksclockpropertyset.htm
old-project: stream
ms.assetid: bf50d4b1-782f-4d15-b6ef-23fa13da68ff
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], IKsClockPropertySet interface [Streaming Media Devices], described, ksproxy/IKsClockPropertySet, ksproxy_0be3eb82-08b7-4afc-a4e5-3815f7499ad0.xml, stream.iksclockpropertyset
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Ksproxy.lib
-	Ksproxy.dll
api_name:
-	IKsClockPropertySet
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsClockPropertySet interface


## -description


The <b>IKsClockPropertySet</b> interface provides methods that let the proxy accurately reflect time.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsClockPropertySet</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsClockPropertySet</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/d9babef4-c41a-4458-8072-eb562ef4d997">KsGetCorrelatedPhysicalTime</a>
</td>
<td align="left" width="63%">
Retrieves the physical time and the correlated system time from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b91f33b3-2706-4c94-9960-ceea023891af">KsGetCorrelatedTime</a>
</td>
<td align="left" width="63%">
Retrieves the presentation time and the correlated system time from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/25875f28-292f-40d9-8b29-ec9af49b0bc0">KsGetPhysicalTime</a>
</td>
<td align="left" width="63%">
Retrieves the current physical time from the underlying clock. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/507d41ae-31b9-4807-99af-9ec48eb2b5aa">KsGetResolution</a>
</td>
<td align="left" width="63%">
Retrieves the clock resolution from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/153e4f47-ae07-4f1e-9ab5-69ef6565ad5d">KsGetState</a>
</td>
<td align="left" width="63%">
Retrieves the streaming state of a pin from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0d22baeb-d08f-4554-9af4-dae9480a471a">KsGetTime</a>
</td>
<td align="left" width="63%">
Retrieves the current presentation time from the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/208fecc5-f01f-41f3-80d3-d811b3f4173a">KsSetCorrelatedPhysicalTime</a>
</td>
<td align="left" width="63%">
Sets the physical time with the correlated system time on the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/58281b50-14b6-4e24-972a-ab3b1d88eb50">KsSetCorrelatedTime</a>
</td>
<td align="left" width="63%">
Sets the correlated system time with the presentation time on the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2f8eb011-1fe1-40f6-b833-50d3e853bffd">KsSetPhysicalTime</a>
</td>
<td align="left" width="63%">
Sets the current physical time on the underlying clock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b1489593-9458-4e78-b59d-c8a780a3a3f1">KsSetTime</a>
</td>
<td align="left" width="63%">
Sets the current presentation time on the underlying clock.

</td>
</tr>
</table> 


## -remarks



The IID for this interface is IID_IKsClockPropertySet.



