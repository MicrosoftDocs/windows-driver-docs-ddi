---
UID: NF:ks.IKsReferenceClock.GetState
title: IKsReferenceClock::GetState (ks.h)
description: The IKsReferenceClock::GetState method queries the associated reference clock for its current streaming state.
old-location: stream\iksreferenceclock_getstate.htm
tech.root: stream
ms.assetid: 5a77a8bc-b477-41b3-bc4e-07c6c14291a1
ms.date: 04/23/2018
keywords: ["IKsReferenceClock::GetState"]
ms.keywords: GetState, GetState method [Streaming Media Devices], GetState method [Streaming Media Devices],IKsReferenceClock interface, IKsReferenceClock interface [Streaming Media Devices],GetState method, IKsReferenceClock.GetState, IKsReferenceClock::GetState, avintfc_e2017894-2e83-4091-84b7-5ea793076b29.xml, ks/IKsReferenceClock::GetState, stream.iksreferenceclock_getstate
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
 - IKsReferenceClock::GetState
 - ks/IKsReferenceClock::GetState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ks.h
api_name:
 - IKsReferenceClock.GetState
---

# IKsReferenceClock::GetState


## -description

The <b>IKsReferenceClock::GetState</b> method queries the associated reference clock for its current streaming state.

## -parameters

### -param State 

[out]
Points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a> structure that indicates the streaming state of the underlying clock.

## -returns

The <b>IKsReferenceClock::GetState</b> method returns STATUS_SUCCESS or  the error code that the relevant clock returned from its <b>GetState</b> property. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-state">KSPROPERTY_CLOCK_STATE</a>.  May return STATUS_DEVICE_NOT_READY if no clock is assigned.

## -remarks

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-clocks">AVStream Clocks</a>.

AVStream uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-clock-state">KSPROPERTY_CLOCK_STATE</a> property to retrieve the correlated time.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspingetreferenceclockinterface">KsPinGetReferenceClockInterface</a>

