---
UID: NC:ks.PFNKSFILTERPROCESS
title: PFNKSFILTERPROCESS (ks.h)
description: An AVStream minidriver's AVStrMiniFilterProcess routine is called when the filter is meant to process frames. It is used to perform Filter-Centric Processing.
tech.root: stream
ms.date: 07/13/2022
keywords: ["PFNKSFILTERPROCESS callback function"]
ms.keywords: AVStrMiniFilterProcess, AVStrMiniFilterProcess routine [Streaming Media Devices], PFNKSFILTERPROCESS, avstclbk_220bff5f-a966-460b-9157-b512cfc9c336.xml, ks/AVStrMiniFilterProcess, stream.avstrminifilterprocess
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
req.irql: (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSFILTERPROCESS
 - ks/PFNKSFILTERPROCESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - PFNKSFILTERPROCESS
---

## -description

An AVStream minidriver's *AVStrMiniFilterProcess* routine is called when the filter is meant to process frames. It is used to perform [Filter-Centric Processing](/windows-hardware/drivers/stream/filter-centric-processing).

## -parameters

### -param Filter [in]

Pointer to the [KSFILTER](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter) structure that must process frames.

### -param Index

Pointer to an array of [KSPROCESSPIN_INDEXENTRY](/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin_indexentry) structures that AVStream orders by pin ID.

## -returns

Return STATUS_SUCCESS to continue processing. Return STATUS_PENDING to stop processing until the next triggering event. The minidriver may return an error code, but this will be treated as described for STATUS_PENDING.

## -remarks

The minidriver specifies this routine's address in the **Process** member of its [KSFILTER_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch) structure.

The routine is called at either IRQL = DISPATCH_LEVEL or PASSIVE_LEVEL depending on the preference expressed in the filter descriptor. Filter descriptors that specify KSFILTER_FLAG_DISPATCH_LEVEL_PROCESSING may have their process callback at DISPATCH_LEVEL; filter descriptors that do not specify this flag will have their process callback at PASSIVE_LEVEL.

For more information, see [Filter-Centric Processing](/windows-hardware/drivers/stream/filter-centric-processing) and [Restarting Processing in AVStream](/windows-hardware/drivers/stream/restarting-processing-in-avstream).

This routine is optional.

## -see-also

[KSFILTER_DISPATCH](/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_dispatch)

[KSPROCESSPIN_INDEXENTRY](/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin_indexentry)
