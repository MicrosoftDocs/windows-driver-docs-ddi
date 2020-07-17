---
UID: NF:ksproxy.IKsClockPropertySet.KsSetPhysicalTime
title: IKsClockPropertySet::KsSetPhysicalTime (ksproxy.h)
description: The KsSetPhysicalTime method sets the physical time on the underlying clock.
old-location: stream\iksclockpropertyset_kssetphysicaltime.htm
tech.root: stream
ms.assetid: 2f8eb011-1fe1-40f6-b833-50d3e853bffd
ms.date: 04/23/2018
keywords: ["IKsClockPropertySet::KsSetPhysicalTime"]
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices],KsSetPhysicalTime method, IKsClockPropertySet.KsSetPhysicalTime, IKsClockPropertySet::KsSetPhysicalTime, KsSetPhysicalTime, KsSetPhysicalTime method [Streaming Media Devices], KsSetPhysicalTime method [Streaming Media Devices],IKsClockPropertySet interface, ksproxy/IKsClockPropertySet::KsSetPhysicalTime, ksproxy_1cebc4eb-efb8-4ec6-97f4-e34fc978fb2f.xml, stream.iksclockpropertyset_kssetphysicaltime
f1_keywords:
 - "ksproxy/IKsClockPropertySet.KsSetPhysicalTime"
 - "IKsClockPropertySet.KsSetPhysicalTime"
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
- IKsClockPropertySet.KsSetPhysicalTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsClockPropertySet::KsSetPhysicalTime


## -description


The <b>KsSetPhysicalTime</b> method sets the physical time on the underlying clock. 


## -parameters




### -param Time [in]

Physical time to which to set the underlying clock.


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



The physical time is based on some underlying physical clock that always progresses, even if the physical type of clock must be changed on the fly. Other physical clocks use an underlying clock's physical time for rate matching.

The proxy uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-physicaltime">KSPROPERTY_CLOCK_PHYSICALTIME</a> property to set the physical time. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetphysicaltime">IKsClockPropertySet::KsGetPhysicalTime</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-physicaltime">KSPROPERTY_CLOCK_PHYSICALTIME</a>
 

 

