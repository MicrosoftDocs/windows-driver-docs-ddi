---
UID: NS:ks.__unnamed_struct_82
title: KSPROPERTY_SERIAL (ks.h)
description: The KSPROPERTY_SERIAL structure is a header that is included for each property that follows a KSPROPERTY_SERIALHDR structure.
old-location: stream\ksproperty_serial.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSPROPERTY_SERIAL structure"]
ms.keywords: "*PKSPROPERTY_SERIAL, KSPROPERTY_SERIAL, KSPROPERTY_SERIAL structure [Streaming Media Devices], PKSPROPERTY_SERIAL, PKSPROPERTY_SERIAL structure pointer [Streaming Media Devices], ks-struct_1d2733c1-6b2a-48e2-ae94-d108a011754e.xml, ks/KSPROPERTY_SERIAL, ks/PKSPROPERTY_SERIAL, stream.ksproperty_serial"
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
req.typenames: KSPROPERTY_SERIAL, *PKSPROPERTY_SERIAL
f1_keywords:
 - PKSPROPERTY_SERIAL
 - ks/PKSPROPERTY_SERIAL
 - KSPROPERTY_SERIAL
 - ks/KSPROPERTY_SERIAL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPROPERTY_SERIAL
---

# KSPROPERTY_SERIAL structure


## -description

The KSPROPERTY_SERIAL structure is a header that is included for each property that follows a KSPROPERTY_SERIALHDR structure.

## -struct-fields

### -field PropTypeSet

A structure of type <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksidentifier">KSIDENTIFIER</a> that specifies the type of property data. This is the same information obtained from querying Basic Support.

### -field Id

Specifies the identifier for this property.

### -field PropertyLength

Specifies the length, in bytes, of the following property data. This does not include any alignment buffering that may be appended to the property data before the next property in the serialization.

## -remarks

A KSPROPERTY_SERIAL structure is followed by the property data, with the start of each property on FILE_LONG_ALIGNMENT. Note that the serial header structure itself is also defined to be on FILE_LONG_ALIGNMENT.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_serialhdr">KSPROPERTY_SERIALHDR</a>
