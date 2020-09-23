---
UID: NS:ks.__unnamed_struct_20
title: KSPROPERTY_POSITIONS (ks.h)
description: The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.
old-location: stream\ksproperty_positions.htm
tech.root: stream
ms.assetid: 869d3a3f-e2f8-4c23-864b-d40f3e67a9ec
ms.date: 04/23/2018
keywords: ["KSPROPERTY_POSITIONS structure"]
ms.keywords: "*PKSPROPERTY_POSITIONS, KSPROPERTY_POSITIONS, KSPROPERTY_POSITIONS structure [Streaming Media Devices], PKSPROPERTY_POSITIONS, PKSPROPERTY_POSITIONS structure pointer [Streaming Media Devices], ks-struct_97829290-4c01-4a03-b56b-3e5915941094.xml, ks/KSPROPERTY_POSITIONS, ks/PKSPROPERTY_POSITIONS, stream.ksproperty_positions"
req.header: ks.h
req.include-header: Ks.h
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
targetos: Windows
req.typenames: KSPROPERTY_POSITIONS, *PKSPROPERTY_POSITIONS
f1_keywords:
 - PKSPROPERTY_POSITIONS
 - ks/PKSPROPERTY_POSITIONS
 - KSPROPERTY_POSITIONS
 - ks/KSPROPERTY_POSITIONS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPROPERTY_POSITIONS
---

# KSPROPERTY_POSITIONS structure


## -description

The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream.

## -struct-fields

### -field Current

Specifies the current position as a 64-bit value.

### -field Stop

Specifies the stop position as a 64-bit value.

### -field CurrentFlags

A structure of type <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ks_seeking_flags">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Current</b> parameter.

### -field StopFlags

A structure of type <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ks_seeking_flags">KS_SEEKING_FLAGS</a> containing flags pertaining to the <b>Stop</b> parameter.

## -remarks

The KSPROPERTY_POSITIONS structure is used with positioning properties in the KSPROPSETID_MediaSeeking property set. These properties correspond to DirectShow's <b>IMediaSeeking::GetPositions</b> and <b>IMediaSeeking::SetPositions</b>.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-mediaseeking-positions">KSPROPERTY_MEDIASEEKING_POSITIONS</a>