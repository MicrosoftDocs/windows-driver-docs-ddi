---
UID: NN:ks.IKsReferenceClock
title: IKsReferenceClock
author: windows-driver-content
description: The IKsReferenceClock interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock.
old-location: stream\iksreferenceclock.htm
old-project: stream
ms.assetid: 92a84bf3-34bf-4ee7-97c0-f5e6427c0464
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _KsEdit
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
req.alt-api: IKsReferenceClock
req.alt-loc: ks.h
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
req.typenames: 
---

# IKsReferenceClock interface



## -description
The <b>IKsReferenceClock</b> interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock.



## -syntax

````
    PIKSREFERENCECLOCK RefClock;

    if (NT_SUCCESS (
      KsPinGetReferenceClockInterface (
        Pin,
        &RefClock)
) {
        ... RefClock -> GetCorrelatedTime (...);
        RefClock -> Release ();
    }
````


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsReferenceClock</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsReferenceClock</b> also has these types of members:

The <b>IKsReferenceClock</b> interface has these methods.

Queries the associated reference clock for the current correlated physical time and system time.

Concurrently queries the associated reference clock for current stream time and acquires the system time. Use if obtaining a time stamp for the <b>PresentationTime</b> member of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>.

Queries the associated reference clock for the current physical time.

Queries the associated reference clock for its resolution.

Queries the associated reference clock for its current state.

Queries the associated reference clock for the current time.

 


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
Concurrently queries the associated reference clock for current stream time and acquires the system time. Use if obtaining a time stamp for the <b>PresentationTime</b> member of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>.

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
</table>Queries the associated reference clock for the current correlated physical time and system time.

Concurrently queries the associated reference clock for current stream time and acquires the system time. Use if obtaining a time stamp for the <b>PresentationTime</b> member of <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>.

Queries the associated reference clock for the current physical time.

Queries the associated reference clock for its resolution.

Queries the associated reference clock for its current state.

Queries the associated reference clock for the current time.

 


## -remarks
The minidriver can acquire an <b>IKsReferenceClock</b> interface by calling <a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>. Because this is a COM-style interface, <b>KsPinGetReferenceClockInterface</b> calls <b>QueryInterface</b>, which in turn invokes <b>AddRef</b> to increment the interface pointer. This means that when the minidriver is finished with the <b>IKsReferenceClock</b> interface, the minidriver must release it by calling <b>Release</b>.

Clients that are written in C will see the <b>IKsReferenceClock</b> interface as a structure that contains a pointer to a table of functions instead of a C++ abstract base class. A client that is written in C++ might do the following:

However, a client that is written in C would do the following instead :

For more information, see <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-kspingetconnectedpininterface.md">KsPinGetConnectedPinInterface</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetconnectedfilterinterface.md">KsPinGetConnectedFilterInterface</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsReferenceClock interface%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

