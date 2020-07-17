---
UID: NC:ks.PFNKSFILTERVOID
title: PFNKSFILTERVOID (ks.h)
description: An AVStream minidriver's AVStrMiniFilterReset routine is called when AVStream receives an IOCTL_KS_RESET_STATE to return the filter to the state it was in at Acquire-time.
old-location: stream\avstrminifilterreset.htm
tech.root: stream
ms.assetid: 8259117b-87ef-410a-955b-6f99966574a6
ms.date: 04/23/2018
keywords: ["PFNKSFILTERVOID callback function"]
ms.keywords: AVStrMiniFilterReset, AVStrMiniFilterReset routine [Streaming Media Devices], PFNKSFILTERVOID, avstclbk_71a3cd5d-faa7-4a7f-a341-deacfbcda051.xml, ks/AVStrMiniFilterReset, stream.avstrminifilterreset
f1_keywords:
 - "ks/AVStrMiniFilterReset"
 - "AVStrMiniFilterReset"
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

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> to return to its previous state.


## -returns



AVStream does not currently use the return value.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>.

Note that it is not the filter in question, but rather a pin on this filter that actually receives the reset IOCTL.

The minidriver specifies this routine's address in the <b>Reset</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch">KSFILTER_DISPATCH</a> structure.

The filter control mutex may be held during this function. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-control-mutex-in-avstream">Filter Control Mutex in AVStream</a>.

This routine is optional.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch">KSFILTER_DISPATCH</a>
 

 

