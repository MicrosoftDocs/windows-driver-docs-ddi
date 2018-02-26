---
UID: NF:ks.IKsReferenceClock.GetPhysicalTime
title: IKsReferenceClock::GetPhysicalTime method
author: windows-driver-content
description: The IKsReferenceClock::GetPhysicalTime method queries the associated reference clock for the current physical time.
old-location: stream\iksreferenceclock_getphysicaltime.htm
old-project: stream
ms.assetid: 96c8d5ef-e9ab-40a6-88e1-56efdb7157b7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, C, G, GetPhysicalTime method [Streaming Media Devices], GetPhysicalTime method [Streaming Media Devices], IKsReferenceClock interface, GetPhysicalTime,IKsReferenceClock.GetPhysicalTime, I, IKsReferenceClock, IKsReferenceClock interface [Streaming Media Devices], GetPhysicalTime method, IKsReferenceClock::GetPhysicalTime, K, P, R, T, a, avintfc_a80ef73b-383a-48b2-b3ea-49e5469c7bca.xml, c, e, f, h, i, k, ks/IKsReferenceClock::GetPhysicalTime, l, m, n, o, r, s, stream.iksreferenceclock_getphysicaltime, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: ks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ks.h
apiname:
-	IKsReferenceClock.GetPhysicalTime
product: Windows
targetos: Windows
req.typenames: 
---

# IKsReferenceClock::GetPhysicalTime method


## -description


The <b>IKsReferenceClock::GetPhysicalTime</b> method queries the associated reference clock for the current physical time.


## -syntax


````
LONGLONG GetPhysicalTime();
````


## -parameters






## -returns



The <b>IKsReferenceClock::GetPhysicalTime</b> method returns the current physical time for the associated pin, specified by default in 100-nanosecond units.




## -remarks



Physical time is tied to a physical clock, either the system clock or an on-board hardware clock.

The physical clock time progresses continuously. Unlike the presentation time, it is not reversible.

Clocks are not required to support a 100-nanosecond resolution. To determine the clock resolution, clients can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a> request.

For more information, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.

AVStream uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565088">KSPROPERTY_CLOCK_PHYSICALTIME</a> property to retrieve the physical time.




## -see-also

<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsReferenceClock::GetPhysicalTime method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

