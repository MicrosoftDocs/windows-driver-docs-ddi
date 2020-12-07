---
UID: NS:ksmedia.__unnamed_struct_88
title: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S (ksmedia.h)
description: The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported.
old-location: stream\ksproperty_allocator_control_capture_caps_s.htm
tech.root: stream
ms.date: 04/30/2019
keywords: ["KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure"]
ms.keywords: "*PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure [Streaming Media Devices], PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, ksmedia/PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, stream.ksproperty_allocator_control_capture_caps_s, vidcapstruct_705f4e1a-dc90-446d-bf3c-97fe454db939.xml"
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
targetos: Windows
req.typenames: KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S, *PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
f1_keywords:
 - PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
 - ksmedia/PKSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
 - KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
 - ksmedia/KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S
---

# KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure


## -description

The KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS_S structure specifies if interleaved capture is supported.

## -struct-fields

### -field InterleavedCapSupported

Indicates whether interleaved capture is supported. Any nonzero value indicates that interleaved capture is supported. A value of zero indicates interleaved capture is not supported.

## -see-also

<a href="/windows-hardware/drivers/stream/ksproperty-allocator-control-capture-caps">KSPROPERTY_ALLOCATOR_CONTROL_CAPTURE_CAPS</a>



<a href="/windows-hardware/drivers/stream/propsetid-allocator-control">PROPSETID_ALLOCATOR_CONTROL</a>
