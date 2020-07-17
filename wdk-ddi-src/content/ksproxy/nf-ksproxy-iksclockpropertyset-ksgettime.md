---
UID: NF:ksproxy.IKsClockPropertySet.KsGetTime
title: IKsClockPropertySet::KsGetTime (ksproxy.h)
description: The KsGetTime method retrieves the time of the underlying clock.
old-location: stream\iksclockpropertyset_ksgettime.htm
tech.root: stream
ms.assetid: 0d22baeb-d08f-4554-9af4-dae9480a471a
ms.date: 04/23/2018
keywords: ["IKsClockPropertySet::KsGetTime"]
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices],KsGetTime method, IKsClockPropertySet.KsGetTime, IKsClockPropertySet::KsGetTime, KsGetTime, KsGetTime method [Streaming Media Devices], KsGetTime method [Streaming Media Devices],IKsClockPropertySet interface, ksproxy/IKsClockPropertySet::KsGetTime, ksproxy_056c73f0-b713-4f86-a38c-a3455e33b773.xml, stream.iksclockpropertyset_ksgettime
f1_keywords:
 - "ksproxy/IKsClockPropertySet.KsGetTime"
 - "IKsClockPropertySet.KsGetTime"
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
- IKsClockPropertySet.KsGetTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsClockPropertySet::KsGetTime


## -description


The <b>KsGetTime</b> method retrieves the time of the underlying clock. 


## -parameters




### -param Time [out]

Pointer to a variable that receives the current clock time.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The proxy uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-time">KSPROPERTY_CLOCK_TIME</a> property to retrieve the current clock time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-kssettime">IKsClockPropertySet::KsSetTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-time">KSPROPERTY_CLOCK_TIME</a>
 

 

