---
UID: NF:ks.IKsReferenceClock.GetPhysicalTime
title: IKsReferenceClock::GetPhysicalTime
author: windows-driver-content
description: The IKsReferenceClock::GetPhysicalTime method queries the associated reference clock for the current physical time.
old-location: stream\iksreferenceclock_getphysicaltime.htm
old-project: stream
ms.assetid: 96c8d5ef-e9ab-40a6-88e1-56efdb7157b7
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: GetPhysicalTime, GetPhysicalTime method [Streaming Media Devices], GetPhysicalTime method [Streaming Media Devices],IKsReferenceClock interface, IKsReferenceClock interface [Streaming Media Devices],GetPhysicalTime method, IKsReferenceClock.GetPhysicalTime, IKsReferenceClock::GetPhysicalTime, avintfc_a80ef73b-383a-48b2-b3ea-49e5469c7bca.xml, ks/IKsReferenceClock::GetPhysicalTime, stream.iksreferenceclock_getphysicaltime
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
-	IKsReferenceClock.GetPhysicalTime
product: Windows
targetos: Windows
req.typenames: 
---

# IKsReferenceClock::GetPhysicalTime


## -description


The <b>IKsReferenceClock::GetPhysicalTime</b> method queries the associated reference clock for the current physical time.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563517">KsPinGetReferenceClockInterface</a>
 

 

