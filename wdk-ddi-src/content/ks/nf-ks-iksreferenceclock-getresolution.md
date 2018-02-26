---
UID: NF:ks.IKsReferenceClock.GetResolution
title: IKsReferenceClock::GetResolution method
author: windows-driver-content
description: The IKsReferenceClock::GetResolution method queries the associated reference clock for its resolution.
old-location: stream\iksreferenceclock_getresolution.htm
old-project: stream
ms.assetid: 7fb70431-db09-470b-b795-826aba3a8b77
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, C, G, GetResolution method [Streaming Media Devices], GetResolution method [Streaming Media Devices], IKsReferenceClock interface, GetResolution,IKsReferenceClock.GetResolution, I, IKsReferenceClock, IKsReferenceClock interface [Streaming Media Devices], GetResolution method, IKsReferenceClock::GetResolution, K, R, avintfc_941baf81-e369-45bc-a798-15270a6d8a29.xml, c, e, f, i, k, ks/IKsReferenceClock::GetResolution, l, n, o, r, s, stream.iksreferenceclock_getresolution, t, u"
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
-	IKsReferenceClock.GetResolution
product: Windows
targetos: Windows
req.typenames: 
---

# IKsReferenceClock::GetResolution method


## -description


The <b>IKsReferenceClock::GetResolution</b> method queries the associated reference clock for its resolution.


## -syntax


````
NTSTATUS GetResolution(
  [out] PKSRESOLUTION Resolution
);
````


## -parameters




### -param Resolution [out]

Specifies granularity and notification error of the clock in a <a href="..\ks\ns-ks-ksresolution.md">KSRESOLUTION</a> structure.


## -returns



The <b>IKsReferenceClock::GetResolution</b> method returns STATUS_SUCCESS or the error code that the relevant clock returned from its <b>GetResolution</b> property. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a>. May return STATUS_DEVICE_NOT_READY if no clock is assigned.




## -remarks



This method retrieves the underlying clock's resolution property, which specifies the clock's increment granularity and notification error in 100-nanosecond units. The finest granularity is one unit; less granular increments contain larger numbers.

The least amount of notification error greater than the clock granularity is zero units; less accurate clocks use larger numbers to indicate  error. The proxy can use this resolution property to determine maximum error and resolution in event notification and synchronization.

For more information, see <a href="https://msdn.microsoft.com/fc1d5bca-72e3-48e2-b46f-09a13bba83b4">AVStream Clocks</a>.

AVStream uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565092">KSPROPERTY_CLOCK_RESOLUTION</a> property to retrieve the clock resolution.




## -see-also

<a href="..\ks\nf-ks-kspingetreferenceclockinterface.md">KsPinGetReferenceClockInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsReferenceClock::GetResolution method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

