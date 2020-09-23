---
UID: NS:ks.__unnamed_struct_55
title: KSFRAMETIME (ks.h)
description: The KSFRAMETIME structure is supported by rendering pins, and is used to return the duration of the next frame of data, and flags associated with that frame.
old-location: stream\ksframetime.htm
tech.root: stream
ms.assetid: 0e3beb72-2b00-41be-a7b4-341bcf065e92
ms.date: 06/25/2020
keywords: ["KSFRAMETIME structure"]
ms.keywords: "*PKSFRAMETIME, KSFRAMETIME, KSFRAMETIME structure [Streaming Media Devices], PKSFRAMETIME, PKSFRAMETIME structure pointer [Streaming Media Devices], ks-struct_3abc9b81-d7e7-455c-a577-2efa7c986cc5.xml, ks/KSFRAMETIME, ks/PKSFRAMETIME, stream.ksframetime"
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
req.typenames: KSFRAMETIME, *PKSFRAMETIME
f1_keywords:
 - PKSFRAMETIME
 - ks/PKSFRAMETIME
 - KSFRAMETIME
 - ks/KSFRAMETIME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSFRAMETIME
---

# KSFRAMETIME structure


## -description

The KSFRAMETIME structure is supported by rendering pins, and is used to return the duration of the next frame of data, and flags associated with that frame.

## -struct-fields

### -field Duration

Specifies the duration in presentation time units.

### -field FrameFlags

Specifies the flags specific to the next frame, or to all frames. Flags are described on the reference page for [KSALLOCATOR_FRAMING](./ns-ks-ksallocator_framing.md).

### -field Reserved

Set to zero.

## -remarks

Note that this is an optional property, which need only be implemented if the pin instance understands the specifics of the media type it is transporting.