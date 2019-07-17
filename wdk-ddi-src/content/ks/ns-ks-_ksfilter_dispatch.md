---
UID: NS:ks._KSFILTER_DISPATCH
title: _KSFILTER_DISPATCH (ks.h)
description: The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.
old-location: stream\ksfilter_dispatch.htm
tech.root: stream
ms.assetid: 3b84c06f-774e-45e1-9a64-711749bb3a88
ms.date: 04/23/2018
ms.keywords: "*PKSFILTER_DISPATCH, KSFILTER_DISPATCH, KSFILTER_DISPATCH structure [Streaming Media Devices], PKSFILTER_DISPATCH, PKSFILTER_DISPATCH structure pointer [Streaming Media Devices], _KSFILTER_DISPATCH, avstruct_cfadb813-12c3-4960-89d7-72a75db1684a.xml, ks/KSFILTER_DISPATCH, ks/PKSFILTER_DISPATCH, stream.ksfilter_dispatch"
ms.topic: struct
f1_keywords:
 - "ks/KSFILTER_DISPATCH"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSFILTER_DISPATCH
product:
- Windows
targetos: Windows
req.typenames: KSFILTER_DISPATCH, *PKSFILTER_DISPATCH
---

# _KSFILTER_DISPATCH structure


## -description


The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type.


## -struct-fields




### -field Create

Optional. A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksfilterirp">AVStrMiniFilterCreate</a> callback routine.


### -field Close

Optional. A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/previous-versions/ff556307(v=vs.85)">AVStrMiniFilterClose</a> callback routine.


### -field Process

Optional. A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksfilterprocess">AVStrMiniFilterProcess</a> callback routine.


### -field Reset

Optional. A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nc-ks-pfnksfiltervoid">AVStrMiniFilterReset</a> callback routine.


## -remarks



Any of the callback pointers may be <b>NULL</b>, indicating that the driver does not wish to receive notification of a given event.

Also see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/restarting-processing-in-avstream">Restarting Processing in AVStream</a> and 


<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-centric-processing">Filter-Centric Processing</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksprocesspin">KSPROCESSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksprocesspin_indexentry">KSPROCESSPIN_INDEXENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kscompletependingrequest">KsCompletePendingRequest</a>
 

 

