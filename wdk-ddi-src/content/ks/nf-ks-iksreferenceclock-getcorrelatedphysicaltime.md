---
UID: NF:ks.IKsReferenceClock.GetCorrelatedPhysicalTime
title: IKsReferenceClock::GetCorrelatedPhysicalTime (ks.h)
description: The IKsReferenceClock::GetCorrelatedPhysicalTime method queries the associated reference clock for the current physical time and retrieves the correlated system time.
old-location: stream\iksreferenceclock_getcorrelatedphysicaltime.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsReferenceClock::GetCorrelatedPhysicalTime"]
ms.keywords: GetCorrelatedPhysicalTime, GetCorrelatedPhysicalTime method [Streaming Media Devices], GetCorrelatedPhysicalTime method [Streaming Media Devices],IKsReferenceClock interface, IKsReferenceClock interface [Streaming Media Devices],GetCorrelatedPhysicalTime method, IKsReferenceClock.GetCorrelatedPhysicalTime, IKsReferenceClock::GetCorrelatedPhysicalTime, avintfc_d0686a3a-47ab-4dbc-87ec-ee56e357b4ea.xml, ks/IKsReferenceClock::GetCorrelatedPhysicalTime, stream.iksreferenceclock_getcorrelatedphysicaltime
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
 - IKsReferenceClock::GetCorrelatedPhysicalTime
 - ks/IKsReferenceClock::GetCorrelatedPhysicalTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ks.h
api_name:
 - IKsReferenceClock::GetCorrelatedPhysicalTime
---

# IKsReferenceClock::GetCorrelatedPhysicalTime


## -description

The <b>IKsReferenceClock::GetCorrelatedPhysicalTime</b> method queries the associated reference clock for the current physical time and retrieves the correlated system time.

## -parameters

### -param SystemTime [out]


Specifies the current system time in 100 nanosecond units.

## -returns

The <b>IKsReferenceClock::GetCorrelatedPhysicalTime</b> method returns the current physical clock time, specified by default in 100-nanosecond units. The correlated system time is returned in <i>SystemTime</i>.

## -remarks

Use this method to determine the difference between physical time and system time. <b>IKsReferenceClock::GetCorrelatedPhysicalTime</b> returns the times that both clocks show at the same moment.

For more information, see <a href="/windows-hardware/drivers/stream/avstream-clocks">AVStream Clocks</a>.

AVStream uses the <a href="/windows-hardware/drivers/stream/ksproperty-clock-correlatedphysicaltime">KSPROPERTY_CLOCK_CORRELATEDPHYSICALTIME</a> property to retrieve the correlated physical time.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetreferenceclockinterface">KsPinGetReferenceClockInterface</a>

