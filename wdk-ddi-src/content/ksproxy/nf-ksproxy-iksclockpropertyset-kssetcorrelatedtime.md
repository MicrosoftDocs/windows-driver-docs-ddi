---
UID: NF:ksproxy.IKsClockPropertySet.KsSetCorrelatedTime
title: IKsClockPropertySet::KsSetCorrelatedTime method
author: windows-driver-content
description: The KsSetCorrelatedTime method sets the current time with the correlated system time on the underlying clock.
old-location: stream\iksclockpropertyset_kssetcorrelatedtime.htm
old-project: stream
ms.assetid: 58281b50-14b6-4e24-972a-ab3b1d88eb50
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsClockPropertySet, IKsClockPropertySet interface [Streaming Media Devices], KsSetCorrelatedTime method, IKsClockPropertySet::KsSetCorrelatedTime, KsSetCorrelatedTime method [Streaming Media Devices], KsSetCorrelatedTime method [Streaming Media Devices], IKsClockPropertySet interface, KsSetCorrelatedTime,IKsClockPropertySet.KsSetCorrelatedTime, ksproxy/IKsClockPropertySet::KsSetCorrelatedTime, ksproxy_bf409d47-cdd4-467e-88f1-4358bf8934d4.xml, stream.iksclockpropertyset_kssetcorrelatedtime
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: ksproxy.h
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
-	IKsClockPropertySet.KsSetCorrelatedTime
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsClockPropertySet::KsSetCorrelatedTime method


## -description


The <b>KsSetCorrelatedTime</b> method sets the current time with the correlated system time on the underlying clock. 


## -syntax


````
HRESULT KsSetCorrelatedTime(
  [in] KSCORRELATED_TIME *CorrelatedTime
);
````


## -parameters




### -param CorrelatedTime [in]

Pointer to a <a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a> structure that contains the current clock time along with the correlated system time to which to set the underlying clock. 


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The proxy uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a> property to set the correlated time. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559738">IKsClockPropertySet::KsGetCorrelatedTime</a>



<a href="..\ks\ns-ks-kscorrelated_time.md">KSCORRELATED_TIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564465">KSPROPERTY_CLOCK_CORRELATEDTIME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsClockPropertySet::KsSetCorrelatedTime method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

