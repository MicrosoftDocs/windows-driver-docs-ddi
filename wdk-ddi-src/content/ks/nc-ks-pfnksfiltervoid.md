---
UID: NC:ks.PFNKSFILTERVOID
title: PFNKSFILTERVOID (ks.h)
description: An AVStream minidriver's AVStrMiniFilterReset routine is called when AVStream receives an IOCTL_KS_RESET_STATE to return the filter to the state it was in at Acquire-time.
old-location: stream\avstrminifilterreset.htm
tech.root: stream
ms.assetid: 8259117b-87ef-410a-955b-6f99966574a6
ms.date: 04/23/2018
ms.keywords: AVStrMiniFilterReset, AVStrMiniFilterReset routine [Streaming Media Devices], PFNKSFILTERVOID, avstclbk_71a3cd5d-faa7-4a7f-a341-deacfbcda051.xml, ks/AVStrMiniFilterReset, stream.avstrminifilterreset
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
- UserDefined
api_location:
- ks.h
api_name:
- AVStrMiniFilterReset
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSFILTERVOID callback function


## -description


An AVStream minidriver's <i>AVStrMiniFilterReset</i> routine is called when AVStream receives an IOCTL_KS_RESET_STATE to return the filter to the state it was in at <i>Acquire</i>-time. This routine is also called when a queue associated with a pin on the filter is flushed. <i>This routine will only be called for a filter-centric filter</i>.


## -parameters




### -param Filter [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> to return to its previous state.


## -returns



AVStream does not currently use the return value.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/e56c5102-7ea6-4687-ae5e-1550db9500f0">Filter-Centric Processing</a>.

Note that it is not the filter in question, but rather a pin on this filter that actually receives the reset IOCTL.

The minidriver specifies this routine's address in the <b>Reset</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a> structure.

The filter control mutex may be held during this function. See <a href="https://msdn.microsoft.com/402795a0-e567-4e7e-a7d8-b2ce29ffb8fd">Filter Control Mutex in AVStream</a>.

This routine is optional.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562554">KSFILTER_DISPATCH</a>
 

 

