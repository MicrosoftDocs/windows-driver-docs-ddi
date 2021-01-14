---
UID: NS:ks._KSFILTER_DISPATCH
title: _KSFILTER_DISPATCH (ks.h)
description: The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.
old-location: stream\ksfilter_dispatch.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSFILTER_DISPATCH structure"]
ms.keywords: "*PKSFILTER_DISPATCH, KSFILTER_DISPATCH, KSFILTER_DISPATCH structure [Streaming Media Devices], PKSFILTER_DISPATCH, PKSFILTER_DISPATCH structure pointer [Streaming Media Devices], _KSFILTER_DISPATCH, avstruct_cfadb813-12c3-4960-89d7-72a75db1684a.xml, ks/KSFILTER_DISPATCH, ks/PKSFILTER_DISPATCH, stream.ksfilter_dispatch"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.typenames: KSFILTER_DISPATCH, *PKSFILTER_DISPATCH
f1_keywords:
 - _KSFILTER_DISPATCH
 - ks/_KSFILTER_DISPATCH
 - PKSFILTER_DISPATCH
 - ks/PKSFILTER_DISPATCH
 - KSFILTER_DISPATCH
 - ks/KSFILTER_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - _KSFILTER_DISPATCH
 - PKSFILTER_DISPATCH
 - KSFILTER_DISPATCH
---

# _KSFILTER_DISPATCH structure


## -description

The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.

## -struct-fields

### -field Create

Optional. A pointer to a minidriver-supplied <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksfilterirp">AVStrMiniFilterCreate</a> callback routine.

### -field Close

Optional. A pointer to a minidriver-supplied <a href="/previous-versions/ff556307(v=vs.85)">AVStrMiniFilterClose</a> callback routine.

### -field Process

Optional. A pointer to a minidriver-supplied <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksfilterprocess">AVStrMiniFilterProcess</a> callback routine.

### -field Reset

Optional. A pointer to a minidriver-supplied <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnksfiltervoid">AVStrMiniFilterReset</a> callback routine.

## -remarks

Any of the callback pointers may be <b>NULL</b>, indicating that the driver does not wish to receive notification of a given event.

Also see <a href="/windows-hardware/drivers/stream/restarting-processing-in-avstream">Restarting Processing in AVStream</a> and 


<a href="/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin">KSPROCESSPIN</a>



<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscompletependingrequest">KsCompletePendingRequest</a>

