---
UID: NF:ks.IKsReferenceClock.GetResolution
title: IKsReferenceClock::GetResolution
author: windows-driver-content
description: The IKsReferenceClock::GetResolution method queries the associated reference clock for its resolution.
old-location: stream\iksreferenceclock_getresolution.htm
tech.root: stream
ms.assetid: 7fb70431-db09-470b-b795-826aba3a8b77
ms.date: 4/23/2018
ms.keywords: GetResolution, GetResolution method [Streaming Media Devices], GetResolution method [Streaming Media Devices],IKsReferenceClock interface, IKsReferenceClock interface [Streaming Media Devices],GetResolution method, IKsReferenceClock.GetResolution, IKsReferenceClock::GetResolution, avintfc_941baf81-e369-45bc-a798-15270a6d8a29.xml, ks/IKsReferenceClock::GetResolution, stream.iksreferenceclock_getresolution
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
-	IKsReferenceClock.GetResolution
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsReferenceClock::GetResolution


## -description


The <b>IKsReferenceClock::GetResolution</b> method queries the associated reference clock for its resolution.


## -parameters




### -param Resolution [out]

Specifies granularity and notification error of the clock in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566806">KSRESOLUTION</a> structure.


## -returns



The <b>IKsReferenceClock::GetResolution</b> method returns STATUS_SUCCESS or the error code that the relevant clock returned from its <b>GetResolution</b> property. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>. May return STATUS_DEVICE_NOT_READY if no clock is assigned.




## -remarks



This method retrieves the underlying clock's resolution property, which specifies the clock's increment granularity and notification error in 100-nanosecond units. The finest granularity is one unit; less granular increments contain larger numbers.

The least amount of notification error greater than the clock granularity is zero units; less accurate clocks use larger numbers to indicate  error. The proxy can use this resolution property to determine maximum error and resolution in event notification and synchronization.

For more information, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.

AVStream uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a> property to retrieve the clock resolution.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563517">KsPinGetReferenceClockInterface</a>
 

 

