---
UID: NF:ks.KsFilterGetFirstChildPin
title: KsFilterGetFirstChildPin function (ks.h)
description: The KsFilterGetFirstChildPin function returns the first instantiated pin of type PinID on the filter specified by Filter.
old-location: stream\ksfiltergetfirstchildpin.htm
tech.root: stream
ms.assetid: b026908a-51d4-45a8-9c0e-1c163563bfbf
ms.date: 04/23/2018
keywords: ["KsFilterGetFirstChildPin function"]
ms.keywords: KsFilterGetFirstChildPin, KsFilterGetFirstChildPin function [Streaming Media Devices], avfunc_303477ee-598b-4b5b-baae-1e520c154e99.xml, ks/KsFilterGetFirstChildPin, stream.ksfiltergetfirstchildpin
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsFilterGetFirstChildPin
 - ks/KsFilterGetFirstChildPin
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsFilterGetFirstChildPin
---

# KsFilterGetFirstChildPin function


## -description

The<b> KsFilterGetFirstChildPin</b> function returns the first instantiated pin of type <i>PinID</i> on the filter specified by <i>Filter</i>.

## -parameters

### -param Filter 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure to query for instantiated pins.

### -param PinId 

[in]
The numeric ID of the pin type for which to find the first instantiated member.

## -returns

<b>KsFilterGetFirstChildPin</b> returns a pointer to the first instantiated <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure of type <i>PinID</i> on the specified filter.

## -remarks

Note that the object hierarchy is guaranteed stable only while the appropriate mutex is held, in this case the filter control mutex. For more information, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksfiltergetchildpincount">KsFilterGetChildPinCount</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetnextsiblingpin">KsPinGetNextSiblingPin</a>