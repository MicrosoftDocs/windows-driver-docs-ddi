---
UID: NF:ksproxy.IKsClockPropertySet.KsSetCorrelatedTime
title: IKsClockPropertySet::KsSetCorrelatedTime (ksproxy.h)
description: The KsSetCorrelatedTime method sets the current time with the correlated system time on the underlying clock.
old-location: stream\iksclockpropertyset_kssetcorrelatedtime.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsClockPropertySet::KsSetCorrelatedTime"]
ms.keywords: IKsClockPropertySet interface [Streaming Media Devices],KsSetCorrelatedTime method, IKsClockPropertySet.KsSetCorrelatedTime, IKsClockPropertySet::KsSetCorrelatedTime, KsSetCorrelatedTime, KsSetCorrelatedTime method [Streaming Media Devices], KsSetCorrelatedTime method [Streaming Media Devices],IKsClockPropertySet interface, ksproxy/IKsClockPropertySet::KsSetCorrelatedTime, ksproxy_bf409d47-cdd4-467e-88f1-4358bf8934d4.xml, stream.iksclockpropertyset_kssetcorrelatedtime
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsClockPropertySet::KsSetCorrelatedTime
 - ksproxy/IKsClockPropertySet::KsSetCorrelatedTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsClockPropertySet.KsSetCorrelatedTime
---

# IKsClockPropertySet::KsSetCorrelatedTime


## -description

The <b>KsSetCorrelatedTime</b> method sets the current time with the correlated system time on the underlying clock.

## -parameters

### -param CorrelatedTime 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-kscorrelated_time">KSCORRELATED_TIME</a> structure that contains the current clock time along with the correlated system time to which to set the underlying clock.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

The proxy uses the <a href="/windows-hardware/drivers/stream/ksproperty-clock-correlatedtime">KSPROPERTY_CLOCK_CORRELATEDTIME</a> property to set the correlated time.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksclockpropertyset-ksgetcorrelatedtime">IKsClockPropertySet::KsGetCorrelatedTime</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-kscorrelated_time">KSCORRELATED_TIME</a>



<a href="/windows-hardware/drivers/stream/ksproperty-clock-correlatedtime">KSPROPERTY_CLOCK_CORRELATEDTIME</a>
