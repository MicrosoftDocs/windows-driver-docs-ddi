---
UID: NN:ks.IKsReferenceClock
title: IKsReferenceClock (ks.h)
description: The IKsReferenceClock interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock.
old-location: stream\iksreferenceclock.htm
tech.root: stream
ms.assetid: 92a84bf3-34bf-4ee7-97c0-f5e6427c0464
ms.date: 04/23/2018
ms.keywords: IKsReferenceClock, IKsReferenceClock interface [Streaming Media Devices], IKsReferenceClock interface [Streaming Media Devices],described, avintfc_7146002a-d8ab-4789-b752-863f8b2d94d2.xml, ks/IKsReferenceClock, stream.iksreferenceclock
ms.topic: interface
req.header: ks.h
req.include-header: 
req.target-type: Windows
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
- ks.h
api_name:
- IKsReferenceClock
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsReferenceClock interface

## -description

The **IKsReferenceClock** interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock.

## -inheritance

The **IKsReferenceClock** interface inherits from the [IUnknown](https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown) interface.

## -members

The **IKsReferenceClock** interface has these methods.

| Method | Description |
| --- | --- |
| [IKsReferenceClock::GetCorrelatedPhysicalTime](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-iksreferenceclock-getcorrelatedphysicaltime) | Queries the associated reference clock for the current correlated physical time and system time. |
| [IKsReferenceClock::GetCorrelatedTime](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-iksreferenceclock-getcorrelatedtime) | Concurrently queries the associated reference clock for current stream time and acquires the system time. Use if obtaining a time stamp for the **PresentationTime** member of [KSSTREAM_HEADER](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksstream_header). |
| [IKsReferenceClock::GetPhysicalTime](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-iksreferenceclock-getphysicaltime) | Queries the associated reference clock for the current physical time. |
| [IKsReferenceClock::GetResolution](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-iksreferenceclock-getresolution) | Queries the associated reference clock for its resolution. |
| [IKsReferenceClock::GetState](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-iksreferenceclock-getstate) | Queries the associated reference clock for its current state. |
| [IKsReferenceClock::GetTime](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-iksreferenceclock-gettime) | Queries the associated reference clock for the current time. |

## -remarks

The minidriver can acquire an **IKsReferenceClock** interface by calling [KsPinGetReferenceClockInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetreferenceclockinterface). Because this is a COM-style interface, **KsPinGetReferenceClockInterface** calls **QueryInterface**, which in turn invokes **AddRef** to increment the interface pointer. This means that when the minidriver is finished with the **IKsReferenceClock** interface, the minidriver must release it by calling **Release**.

Clients that are written in C will see the **IKsReferenceClock** interface as a structure that contains a pointer to a table of functions instead of a C++ abstract base class. A client that is written in C++ might do the following:

```cpp
PIKSREFERENCECLOCK RefClock;

if (NT_SUCCESS (
  KsPinGetReferenceClockInterface (
    Pin,
    &RefClock)
) {
    ... RefClock -> GetCorrelatedTime (...);
    RefClock -> Release ();
}
```

However, a client that is written in C would do the following instead :

```cpp
PIKSREFERENCECLOCK RefClock;

If (NT_SUCCESS (
  KsPinGetReferenceClockInterface (
    Pin,
    &RefClock)
) {
  ... RefClock -> lpVtbl -> GetCorrelatedTime (...);
  RefClock -> lpVtbl -> Release ();
}
```

For more information, see [AVStream Overview](https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-overview).

## -see-also

[KsPinGetConnectedFilterInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetconnectedfilterinterface)

[KsPinGetConnectedPinInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetconnectedpininterface)

[KsPinGetReferenceClockInterface](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetreferenceclockinterface)
