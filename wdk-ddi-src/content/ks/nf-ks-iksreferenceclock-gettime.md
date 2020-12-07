---
UID: NF:ks.IKsReferenceClock.GetTime
title: IKsReferenceClock::GetTime (ks.h)
description: The IKsReferenceClock::GetTime method queries the associated reference clock for the current time.
old-location: stream\iksreferenceclock_gettime.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsReferenceClock::GetTime"]
ms.keywords: GetTime, GetTime method [Streaming Media Devices], GetTime method [Streaming Media Devices],IKsReferenceClock interface, IKsReferenceClock interface [Streaming Media Devices],GetTime method, IKsReferenceClock.GetTime, IKsReferenceClock::GetTime, avintfc_54820682-eb28-4344-91d3-ee30ef2f7bd6.xml, ks/IKsReferenceClock::GetTime, stream.iksreferenceclock_gettime
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsReferenceClock::GetTime
 - ks/IKsReferenceClock::GetTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ks.h
api_name:
 - IKsReferenceClock.GetTime
---

# IKsReferenceClock::GetTime


## -description

The <b>IKsReferenceClock::GetTime</b> method queries the associated reference clock for the current time.

## -returns

The <b>IKsReferenceClock::GetTime</b> method returns the current stream time for the associated pin, specified by default in 100-nanosecond units.

## -remarks

Do not call this method when obtaining a time stamp for the <b>PresentationTime</b> member of <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a>. Instead, call <a href="/windows-hardware/drivers/ddi/ks/nf-ks-iksreferenceclock-getcorrelatedtime">IKsReferenceClock::GetCorrelatedTime</a> in this situation.

For more information, see <a href="/windows-hardware/drivers/stream/avstream-clocks">AVStream Clocks</a>.

AVStream uses the <a href="/windows-hardware/drivers/stream/ksproperty-clock-time">KSPROPERTY_CLOCK_TIME</a> property to retrieve the current clock time.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetreferenceclockinterface">KsPinGetReferenceClockInterface</a>
