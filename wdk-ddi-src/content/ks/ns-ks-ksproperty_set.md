---
UID: NS:ks.__unnamed_struct_68
title: KSPROPERTY_SET (ks.h)
description: A kernel streaming driver or pin may use the KSPROPERTY_SET structure to describe how it supports a property set.
old-location: stream\ksproperty_set.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSPROPERTY_SET structure"]
ms.keywords: "*PKSPROPERTY_SET, KSPROPERTY_SET, KSPROPERTY_SET structure [Streaming Media Devices], PKSPROPERTY_SET, PKSPROPERTY_SET structure pointer [Streaming Media Devices], ks-struct_2c865d90-5142-4cda-bbd2-af67ac716c87.xml, ks/KSPROPERTY_SET, ks/PKSPROPERTY_SET, stream.ksproperty_set"
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
req.typenames: KSPROPERTY_SET, *PKSPROPERTY_SET
f1_keywords:
 - PKSPROPERTY_SET
 - ks/PKSPROPERTY_SET
 - KSPROPERTY_SET
 - ks/KSPROPERTY_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSPROPERTY_SET
 - KSPROPERTY_SET
---

# KSPROPERTY_SET structure


## -description

A kernel streaming driver or pin may use the KSPROPERTY_SET structure to describe how it supports a property set.

## -struct-fields

### -field Set

Specifies the GUID that identifies the property set.

### -field PropertiesCount

Specifies the size of the array pointed to by the <b>PropertyItem</b> member.

### -field PropertyItem

Points to the beginning of an array of <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item">KSPROPERTY_ITEM</a> structures that describe how the driver or pin supports each property in the set.

### -field FastIoCount

Reserved for system use.

### -field FastIoTable

A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksfastproperty_item">KSFASTPROPERTY_ITEM</a> structure. This member is reserved for system use.

## -remarks

For more information, see <a href="/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item">KSPROPERTY_ITEM</a>

