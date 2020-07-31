---
UID: NF:ksproxy.IKsClockPropertySet.KsSetTime
title: IKsClockPropertySet::KsSetTime (ksproxy.h)
description: The KsSetTime method sets the current time on the underlying clock.
old-location: stream\iksclockpropertyset_kssettime.htm
tech.root: stream
ms.assetid: b1489593-9458-4e78-b59d-c8a780a3a3f1
ms.date: 04/23/2018
keywords: ["IKsClockPropertySet::KsSetTime"]
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices],KsSetTime method, IKsClockPropertySet.KsSetTime, IKsClockPropertySet::KsSetTime, KsSetTime, KsSetTime method [Streaming Media Devices], KsSetTime method [Streaming Media Devices],IKsClockPropertySet interface, ksproxy/IKsClockPropertySet::KsSetTime, ksproxy_6d169c35-dd1b-4ccb-b028-f6a8d19e51ea.xml, stream.iksclockpropertyset_kssettime
f1_keywords:
 - "ksproxy/IKsClockPropertySet.KsSetTime"
 - "IKsClockPropertySet.KsSetTime"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsClockPropertySet.KsSetTime
targetos: Windows
req.typenames: 
---

# IKsClockPropertySet::KsSetTime


## -description


The <b>KsSetTime</b> method sets the current time on the underlying clock.


## -parameters




### -param Time [in]

Time to which to set the underlying clock.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The proxy uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-time">KSPROPERTY_CLOCK_TIME</a> property to set the current clock time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgettime">IKsClockPropertySet::KsGetTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-time">KSPROPERTY_CLOCK_TIME</a>
 

 

