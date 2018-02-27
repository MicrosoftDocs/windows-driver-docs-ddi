---
UID: NF:ks.IKsReferenceClock.GetCorrelatedPhysicalTime
title: IKsReferenceClock::GetCorrelatedPhysicalTime method
author: windows-driver-content
description: The IKsReferenceClock::GetCorrelatedPhysicalTime method queries the associated reference clock for the current physical time and retrieves the correlated system time.
old-location: stream\iksreferenceclock_getcorrelatedphysicaltime.htm
old-project: stream
ms.assetid: b80f6e20-410d-4984-8535-782a84c6af7e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetCorrelatedPhysicalTime method [Streaming Media Devices], GetCorrelatedPhysicalTime method [Streaming Media Devices], IKsReferenceClock interface, GetCorrelatedPhysicalTime,IKsReferenceClock.GetCorrelatedPhysicalTime, IKsReferenceClock, IKsReferenceClock interface [Streaming Media Devices], GetCorrelatedPhysicalTime method, IKsReferenceClock::GetCorrelatedPhysicalTime, avintfc_d0686a3a-47ab-4dbc-87ec-ee56e357b4ea.xml, ks/IKsReferenceClock::GetCorrelatedPhysicalTime, stream.iksreferenceclock_getcorrelatedphysicaltime
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ks.h
api_name:
-	IKsReferenceClock.GetCorrelatedPhysicalTime
product: Windows
targetos: Windows
req.typenames: 
---

# IKsReferenceClock::GetCorrelatedPhysicalTime method


## -description


The <b>IKsReferenceClock::GetCorrelatedPhysicalTime</b> method queries the associated reference clock for the current physical time and retrieves the correlated system time.  


## -syntax


````
LONGLONG GetCorrelatedPhysicalTime(
  [out] PLONGLONG SystemTime
);
````


## -parameters




### -param SystemTime [out]

Specifies the current system time in 100 nanosecond units.


## -returns



The <b>IKsReferenceClock::GetCorrelatedPhysicalTime</b> method returns the current physical clock time, specified by default in 100-nanosecond units. The correlated system time is returned in <i>SystemTime</i>.




## -remarks



Use this method to determine the difference between physical time and system time. <b>IKsReferenceClock::GetCorrelatedPhysicalTime</b> returns the times that both clocks show at the same moment.

For more information, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.

AVStream uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564461">KSPROPERTY_CLOCK_CORRELATEDPHYSICALTIME</a> property to retrieve the correlated physical time.




## -see-also

<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsReferenceClock::GetCorrelatedPhysicalTime method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

