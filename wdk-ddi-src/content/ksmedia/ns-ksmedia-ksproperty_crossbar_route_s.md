---
UID: NS:ksmedia.__unnamed_struct_143
title: KSPROPERTY_CROSSBAR_ROUTE_S (ksmedia.h)
description: The KSPROPERTY_CROSSBAR_ROUTE_S structure describes whether a particular routing is possible and specifies the current routing for a pin.
old-location: stream\ksproperty_crossbar_route_s.htm
tech.root: stream
ms.assetid: 0db68fcd-8661-41d2-ac95-e9b6033e6aa8
ms.date: 04/23/2018
keywords: ["KSPROPERTY_CROSSBAR_ROUTE_S structure"]
ms.keywords: "*PKSPROPERTY_CROSSBAR_ROUTE_S, KSPROPERTY_CROSSBAR_ROUTE_S, KSPROPERTY_CROSSBAR_ROUTE_S structure [Streaming Media Devices], PKSPROPERTY_CROSSBAR_ROUTE_S, PKSPROPERTY_CROSSBAR_ROUTE_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CROSSBAR_ROUTE_S, ksmedia/PKSPROPERTY_CROSSBAR_ROUTE_S, stream.ksproperty_crossbar_route_s, vidcapstruct_a1d08316-6a91-4f40-93d2-b371c6e35eff.xml"
f1_keywords:
 - "ksmedia/KSPROPERTY_CROSSBAR_ROUTE_S"
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
- HeaderDef
api_location:
- ksmedia.h
api_name:
- KSPROPERTY_CROSSBAR_ROUTE_S
product:
- Windows
targetos: Windows
req.typenames: KSPROPERTY_CROSSBAR_ROUTE_S, *PKSPROPERTY_CROSSBAR_ROUTE_S
---

# KSPROPERTY_CROSSBAR_ROUTE_S structure


## -description


The KSPROPERTY_CROSSBAR_ROUTE_S structure describes whether a particular routing is possible and specifies the current routing for a pin.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field IndexInputPin

Specifies the zero-based index of the input pin for which the query is being made.


### -field IndexOutputPin

Specifies the zero-based index of the output pin for which the query is being made.


### -field CanRoute

Returns whether the minidriver supports routing between the pins specified by <b>IndexInputPin</b> and <b>IndexOutputPin</b>. A nonzero value indicates that routing is supported. If the minidriver does not support routing between the two pins, this value is zero.


## -remarks



If the value of <b>IndexInputPin</b> is (-1) on an audio output pin, then the audio stream should be muted.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-crossbar-route">KSPROPERTY_CROSSBAR_ROUTE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/propsetid-vidcap-crossbar">PROPSETID_VIDCAP_CROSSBAR</a>
 

 

