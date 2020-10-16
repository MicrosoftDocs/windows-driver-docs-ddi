---
UID: NS:ks.__unnamed_struct_65
title: KSPROPERTY_VALUES (ks.h)
description: The KSPROPERTY_VALUES structure describes the type and acceptable default values of a property.
old-location: stream\ksproperty_values.htm
tech.root: stream
ms.assetid: 0837f458-6585-4ac9-a166-e72f715238a1
ms.date: 10/16/2020
keywords: ["KSPROPERTY_VALUES structure"]
ms.keywords: "*PKSPROPERTY_VALUES, KSPROPERTY_VALUES, KSPROPERTY_VALUES structure [Streaming Media Devices], PKSPROPERTY_VALUES, PKSPROPERTY_VALUES structure pointer [Streaming Media Devices], ks-struct_a9156948-e21f-41d4-bb63-9c85fdbf57f3.xml, ks/KSPROPERTY_VALUES, ks/PKSPROPERTY_VALUES, stream.ksproperty_values"
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
req.typenames: KSPROPERTY_VALUES, *PKSPROPERTY_VALUES
f1_keywords:
 - PKSPROPERTY_VALUES
 - ks/PKSPROPERTY_VALUES
 - KSPROPERTY_VALUES
 - ks/KSPROPERTY_VALUES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPROPERTY_VALUES
---

# KSPROPERTY_VALUES structure

## -description

The KSPROPERTY_VALUES structure describes the type and acceptable default values of a property.

## -struct-fields

### -field PropTypeSet

Specifies a KSIDENTIFIER structure (see [KSEVENT](/previous-versions/ff561744(v=vs.85))) that identifies the data type of the property. The **Set** member of a KSIDENTIFIER structure indicates the set of value types supported, and the **Id** member of the same structure identifies the type within the set.

### -field MembersListCount

Specifies the number of entries in the array pointed to by **MembersList**.

### -field MembersList

Points to an array of [KSPROPERTY_MEMBERSLIST](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist) structures. Each entry specifies a list of possible values or sets of values that the property may assume.

## -remarks

**PropTypeSet.Set** almost always equals KSPROPTYPESETID_General. The individual value types in KSPROPTYPESETID_General correspond to the VARENUM types documented in the Microsoft Windows SDK.

Possible values for PropTypeSet.Id in streaming media (audio/camera) include:

| Value | Data type |
|--|--|
| VT_BLOB | Length-prefixed bytes. |
| VT_BOOL | A Boolean value. True is -1 and false is 0. |
| VT_CLSID | A class ID. |
| VT_I4 | A 4-byte integer. |
| VT_ILLEGAL | An illegal value. |
| VT_LPWSTR | A wide null-terminated string. |
| VT_R8 | An 8-byte real. |
| VT_UI1 | An unsigned character. |
| VT_UI2 | An unsigned short. |
| VT_UI4 | An unsigned 4-byte integer. |
| VT_UI8 | An unsigned 8-byte integer. |

For more information, see [VARENUM enumeration (ks.h)](/windows-hardware/drivers/ddi/ks/ne-ks-varenum).

A driver can specify a pointer to a KSPROPERTY_VALUES structure in the relevant KSPROPERTY_ITEM for a property.

For more information, see [KS Properties](/windows-hardware/drivers/stream/ks-properties).

## -see-also

[KSEVENT](/previous-versions/ff561744(v=vs.85))

[KSPROPERTY_DESCRIPTION](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_description)

[KSPROPERTY_ITEM](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item)

[KSPROPERTY_MEMBERSLIST](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist)
