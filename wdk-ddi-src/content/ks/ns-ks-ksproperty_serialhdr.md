---
UID: NS:ks.__unnamed_struct_81
title: KSPROPERTY_SERIALHDR (ks.h)
description: The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties.
old-location: stream\ksproperty_serialhdr.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSPROPERTY_SERIALHDR structure"]
ms.keywords: "*PKSPROPERTY_SERIALHDR, KSPROPERTY_SERIALHDR, KSPROPERTY_SERIALHDR structure [Streaming Media Devices], PKSPROPERTY_SERIALHDR, PKSPROPERTY_SERIALHDR structure pointer [Streaming Media Devices], ks-struct_cdf54d37-a5b8-4a73-98dd-c7a9439ac51a.xml, ks/KSPROPERTY_SERIALHDR, ks/PKSPROPERTY_SERIALHDR, stream.ksproperty_serialhdr"
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
req.typenames: KSPROPERTY_SERIALHDR, *PKSPROPERTY_SERIALHDR
f1_keywords:
 - PKSPROPERTY_SERIALHDR
 - ks/PKSPROPERTY_SERIALHDR
 - KSPROPERTY_SERIALHDR
 - ks/KSPROPERTY_SERIALHDR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPROPERTY_SERIALHDR
---

# KSPROPERTY_SERIALHDR structure


## -description

The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties.

## -struct-fields

### -field PropertySet

Specifies the GUID of the property set contained in the serialized buffer.

### -field Count

Specifies the count of serialized properties to follow.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_serial">KSPROPERTY_SERIAL</a>
