---
UID: NC:ks.PFNKSFILTERPROCESS
title: PFNKSFILTERPROCESS (ks.h)
description: An AVStream minidriver's AVStrMiniFilterProcess routine is called when the filter is meant to process frames. It is used to perform Filter-Centric Processing.
old-location: stream\avstrminifilterprocess.htm
tech.root: stream
ms.assetid: f1998d68-1c9e-4527-a174-b22a8c301e63
ms.date: 04/23/2018
ms.keywords: AVStrMiniFilterProcess, AVStrMiniFilterProcess routine [Streaming Media Devices], PFNKSFILTERPROCESS, avstclbk_220bff5f-a966-460b-9157-b512cfc9c336.xml, ks/AVStrMiniFilterProcess, stream.avstrminifilterprocess
ms.topic: callback
f1_keywords:
 - "ks/AVStrMiniFilterProcess"
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
req.irql: "(See Remarks section)"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- ks.h
api_name:
- AVStrMiniFilterProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNKSFILTERPROCESS callback function


## -description


An AVStream minidriver's <i>AVStrMiniFilterProcess</i> routine is called when the filter is meant to process frames. It is used to perform <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>.


## -parameters




### -param Filter [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter">KSFILTER</a> structure that must process frames.


### -param Index








#### - ProcessPinsIndex [in]

Pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a> structures that AVStream orders by pin ID.


## -returns



Return STATUS_SUCCESS to continue processing. Return STATUS_PENDING to stop processing until the next triggering event. The minidriver may return an error code, but this will be treated as described for STATUS_PENDING.




## -remarks



The minidriver specifies this routine's address in the <b>Process</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter_dispatch">KSFILTER_DISPATCH</a> structure.

The routine is called at either IRQL = DISPATCH_LEVEL or PASSIVE_LEVEL depending on the preference expressed in the filter descriptor. Filter descriptors that specify KSFILTER_FLAG_DISPATCH_LEVEL_PROCESSING may have their process callback at DISPATCH_LEVEL; filter descriptors that do not specify this flag will have their process callback at PASSIVE_LEVEL.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/restarting-processing-in-avstream">Restarting Processing in AVStream</a>.

This routine is optional.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter_dispatch">KSFILTER_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a>
 

 

