---
UID: NS:ks.__unnamed_struct_7
title: KSPROPERTY_DESCRIPTION (ks.h)
description: The KSPROPERTY_DESCRIPTION structure specifies the size and type of values contained in a specific property.
old-location: stream\ksproperty_description.htm
tech.root: stream
ms.date: 07/15/2021
keywords: ["KSPROPERTY_DESCRIPTION structure"]
ms.keywords: "*PKSPROPERTY_DESCRIPTION, KSPROPERTY_DESCRIPTION, KSPROPERTY_DESCRIPTION structure [Streaming Media Devices], PKSPROPERTY_DESCRIPTION, PKSPROPERTY_DESCRIPTION structure pointer [Streaming Media Devices], ks-struct_37ee8090-f90e-40a9-8731-3521d1d3a157.xml, ks/KSPROPERTY_DESCRIPTION, ks/PKSPROPERTY_DESCRIPTION, stream.ksproperty_description"
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
req.typenames: KSPROPERTY_DESCRIPTION, *PKSPROPERTY_DESCRIPTION
f1_keywords:
 - PKSPROPERTY_DESCRIPTION
 - ks/PKSPROPERTY_DESCRIPTION
 - KSPROPERTY_DESCRIPTION
 - ks/KSPROPERTY_DESCRIPTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSPROPERTY_DESCRIPTION
 - KSPROPERTY_DESCRIPTION
---

# KSPROPERTY_DESCRIPTION structure

## -description

The **KSPROPERTY_DESCRIPTION** structure specifies the size and type of values contained in a specific property.

## -struct-fields

### -field AccessFlags

Specifies the access allowed to this property. A basic-support request sets this member to the bitwise OR of the flags for all the access types that the handler supports for this property. For a list of possible flag values, see [**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure).

### -field DescriptionSize

Specifies total size in bytes of the **KSPROPERTY_DESCRIPTION** structure and any values entries that follow it. If the basic-support property request returns no values entries, this member is the size of **KSPROPERTY_DESCRIPTION**.

### -field PropTypeSet

A structure of type [**KSIDENTIFIER**](./ns-ks-ksidentifier.md). If supported by the specific property, specifies the type of values contained in this property. This group is uniquely specified by a GUID, such that new types of values may be created without overlapping with extensions to this set. The value types indicate the type of the value (like VT_BOOL, VT_UI4 in the standard set). This is GUID_NULL, with an identifier of zero, if values information is not supported by this property.

### -field MembersListCount

Specifies the number of [**KSPROPERTY_MEMBERSHEADER**](./ns-ks-ksproperty_membersheader.md) structures to follow this header.

### -field Reserved

Reserved for future use. Set to zero.

## -remarks

A driver returns the **KSPROPERTY_DESCRIPTION** structure in response to a basic support property request from a client.

The property values type set is specified by a **KSIDENTIFIER** structure. The basic set supported is [**KSPROPSETID_General**](/windows-hardware/drivers/stream/kspropsetid-general). The identifiers within that set are the standard VARENUM types used for OLE.

The values information that may follow the **KSPROPERTY_DESCRIPTION** structure is described by a list of [**KSPROPERTY_MEMBERSLIST**](./ns-ks-ksproperty_memberslist.md) structures, each of which contains data range information.

For more information, see [KS Properties](/windows-hardware/drivers/stream/ks-properties).

## -see-also

[**KSIDENTIFIER**](./ns-ks-ksidentifier.md)

[**KSPROPERTY**](/windows-hardware/drivers/stream/ksproperty-structure)

[**KSPROPERTY_ITEM**](./ns-ks-ksproperty_item.md)

[**KSPROPERTY_MEMBERSHEADER**](./ns-ks-ksproperty_membersheader.md)

[**KSPROPERTY_VALUES**](./ns-ks-ksproperty_values.md)