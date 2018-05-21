---
UID: NN:ks.IKsReferenceClock
title: IKsReferenceClock
author: windows-driver-content
description: The IKsReferenceClock interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock.
old-location: stream\iksreferenceclock.htm
old-project: stream
ms.assetid: 92a84bf3-34bf-4ee7-97c0-f5e6427c0464
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: IKsReferenceClock, IKsReferenceClock interface [Streaming Media Devices], IKsReferenceClock interface [Streaming Media Devices],described, avintfc_7146002a-d8ab-4789-b752-863f8b2d94d2.xml, ks/IKsReferenceClock, stream.iksreferenceclock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ks.h
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
-	ks.h
api_name:
-	IKsReferenceClock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsReferenceClock interface


## -description


The <b>IKsReferenceClock</b> interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsReferenceClock</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IKsReferenceClock</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IKsReferenceClock</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560726">IKsReferenceClock::GetCorrelatedPhysicalTime</a>
</td>
<td align="left" width="63%">
Queries the associated reference clock for the current correlated physical time and system time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560728">IKsReferenceClock::GetCorrelatedTime</a>
</td>
<td align="left" width="63%">
Concurrently queries the associated reference clock for current stream time and acquires the system time. Use if obtaining a time stamp for the <b>PresentationTime</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560730">IKsReferenceClock::GetPhysicalTime</a>
</td>
<td align="left" width="63%">
Queries the associated reference clock for the current physical time.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560732">IKsReferenceClock::GetResolution</a>
</td>
<td align="left" width="63%">
Queries the associated reference clock for its resolution.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560734">IKsReferenceClock::GetState</a>
</td>
<td align="left" width="63%">
Queries the associated reference clock for its current state.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560736">IKsReferenceClock::GetTime</a>
</td>
<td align="left" width="63%">
Queries the associated reference clock for the current time.

</td>
</tr>
</table> 


## -remarks



The minidriver can acquire an <b>IKsReferenceClock</b> interface by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff563517">KsPinGetReferenceClockInterface</a>. Because this is a COM-style interface, <b>KsPinGetReferenceClockInterface</b> calls <b>QueryInterface</b>, which in turn invokes <b>AddRef</b> to increment the interface pointer. This means that when the minidriver is finished with the <b>IKsReferenceClock</b> interface, the minidriver must release it by calling <b>Release</b>.

Clients that are written in C will see the <b>IKsReferenceClock</b> interface as a structure that contains a pointer to a table of functions instead of a C++ abstract base class. A client that is written in C++ might do the following:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    PIKSREFERENCECLOCK RefClock;

    if (NT_SUCCESS (
      KsPinGetReferenceClockInterface (
        Pin,
        &amp;RefClock)
) {
        ... RefClock -&gt; GetCorrelatedTime (...);
        RefClock -&gt; Release ();
    }</pre>
</td>
</tr>
</table></span></div>
However, a client that is written in C would do the following instead :

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    PIKSREFERENCECLOCK RefClock;

    If (NT_SUCCESS (
      KsPinGetReferenceClockInterface (
        Pin,
        &amp;RefClock)
    ) {
      ... RefClock -&gt; lpVtbl -&gt; GetCorrelatedTime (...);
      RefClock -&gt; lpVtbl -&gt; Release ();
    }</pre>
</td>
</tr>
</table></span></div>
For more information, see <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563506">KsPinGetConnectedFilterInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563509">KsPinGetConnectedPinInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563517">KsPinGetReferenceClockInterface</a>
 

 

