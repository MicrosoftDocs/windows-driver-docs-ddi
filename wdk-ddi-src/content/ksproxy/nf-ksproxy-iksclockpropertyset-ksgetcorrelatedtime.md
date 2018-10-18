---
UID: NF:ksproxy.IKsClockPropertySet.KsGetCorrelatedTime
title: IKsClockPropertySet::KsGetCorrelatedTime
author: windows-driver-content
description: The KsGetCorrelatedTime method retrieves the current time and the correlated system time from the underlying clock.
old-location: stream\iksclockpropertyset_ksgetcorrelatedtime.htm
tech.root: stream
ms.assetid: b91f33b3-2706-4c94-9960-ceea023891af
ms.date: 4/23/2018
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices],KsGetCorrelatedTime method, IKsClockPropertySet.KsGetCorrelatedTime, IKsClockPropertySet::KsGetCorrelatedTime, KsGetCorrelatedTime, KsGetCorrelatedTime method [Streaming Media Devices], KsGetCorrelatedTime method [Streaming Media Devices],IKsClockPropertySet interface, ksproxy/IKsClockPropertySet::KsGetCorrelatedTime, ksproxy_79582c7f-456c-420e-88eb-b0cb6916040f.xml, stream.iksclockpropertyset_ksgetcorrelatedtime
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
-	ksproxy.h
api_name:
-	IKsClockPropertySet.KsGetCorrelatedTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsClockPropertySet::KsGetCorrelatedTime


## -description


The <b>KsGetCorrelatedTime</b> method retrieves the current time and the correlated system time from the underlying clock. 


## -parameters




### -param CorrelatedTime [out]

Pointer to a variable that receives a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561033">KSCORRELATED_TIME</a> structure that contains the current clock time along with the correlated system time.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The <b>KsGetCorrelatedTime</b> method retrieves the current time and the correlated system in an atomic operation. 

The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a> property to retrieve the correlated time. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559756">IKsClockPropertySet::KsSetCorrelatedTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561033">KSCORRELATED_TIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a>
 

 

