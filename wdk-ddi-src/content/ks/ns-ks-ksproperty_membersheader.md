---
UID: NS:ks.KSPROPERTY_MEMBERSHEADER
title: KSPROPERTY_MEMBERSHEADER (ks.h)
description: A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSPROPERTY_MEMBERSHEADER structure"]
ms.keywords: "*PKSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER, KSPROPERTY_MEMBERSHEADER structure [Streaming Media Devices], PKSPROPERTY_MEMBERSHEADER, PKSPROPERTY_MEMBERSHEADER structure pointer [Streaming Media Devices], ks-struct_d43fb5ec-043b-4378-8bdb-aaf80a616150.xml, ks/KSPROPERTY_MEMBERSHEADER, ks/PKSPROPERTY_MEMBERSHEADER, stream.ksproperty_membersheader"
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
req.typenames: KSPROPERTY_MEMBERSHEADER, *PKSPROPERTY_MEMBERSHEADER
f1_keywords:
 - PKSPROPERTY_MEMBERSHEADER
 - ks/PKSPROPERTY_MEMBERSHEADER
 - KSPROPERTY_MEMBERSHEADER
 - ks/KSPROPERTY_MEMBERSHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSPROPERTY_MEMBERSHEADER
 - KSPROPERTY_MEMBERSHEADER
---

## -description

A driver provides a structure of type **KSPROPERTY_MEMBERSHEADER** to describe the size and type of each element in an array containing property values or ranges.

## -struct-fields

### -field MembersFlags

Specifies the type of entries in the members list. The size of valid values is determined by value type, as specified in the **PropTypeSet** member of the [**KSPROPERTY_DESCRIPTION**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_description) structure. The number of range pairs is determined by **MembersCount**. This should be one of the values listed in the following table.

| Value | Description |
|---|---|
| KSPROPERTY_MEMBER_RANGES | Indicates that list members are ranges, of type [**KSPROPERTY_BOUNDS_LONG**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_long) or [KSPROPERTY_BOUNDS_LONGLONG](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_longlong). |
| KSPROPERTY_MEMBER_STEPPEDRANGES | Indicates that the following members are stepped values within ranges, of type [**KSPROPERTY_STEPPING_LONG**](/previous-versions/windows/hardware/drivers/dn936838(v=vs.85)) or [**KSPROPERTY_STEPPING_LONGLONG**](/previous-versions/windows/hardware/drivers/dn936841(v=vs.85)). |
| KSPROPERTY_MEMBER_VALUES | Each entry in the members array is a single value. |

### -field MembersSize

Specifies the size, in bytes, of an individual array element.

### -field MembersCount

Specifies the number of entries in the members array.

### -field Flags

Specifies the type of entries in the members list. The size of valid values is determined by value type, as specified in the **PropTypeSet** member of the [**KSPROPERTY_DESCRIPTION**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_description) structure. The number of range pairs is determined by **MembersCount**. This should be one of the values listed in the following table.

| Value | Description |
|---|---|
| KSPROPERTY_MEMBER_RANGES | Indicates that list members are ranges, of type [**KSPROPERTY_BOUNDS_LONG**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_long) or [**KSPROPERTY_BOUNDS_LONGLONG**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_longlong). |
| KSPROPERTY_MEMBER_STEPPEDRANGES | Indicates that the following members are stepped values within ranges, of type [KSPROPERTY_STEPPING_LONG](/previous-versions/windows/hardware/drivers/dn936838(v=vs.85)) or [**KSPROPERTY_STEPPING_LONGLONG**](/previous-versions/windows/hardware/drivers/dn936841(v=vs.85)). |
| KSPROPERTY_MEMBER_VALUES | Each entry in the members array is a single value. |

## -remarks

The size of the array can be determined by multiplying **MembersCount** by **MembersSize**.

A [**KSPROPERTY_MEMBERSLIST**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist) structure contains a KSPROPERTY_MEMBERSHEADER structure as its first member. The second member, **Members**, points to an array of property values or ranges.

In addition, a [**KSPROPERTY_DESCRIPTION**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_description) structure can be followed by a list of KSPROPERTY_MEMBERSHEADER structures.

For more information about KSPROPERTY_MEMBER_FLAG_DEFAULT, see [KSPROPERTY_ITEM](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item). For more information about KSPROPERTY_MEMBER_FLAG_BASICSUPPORT_MULTICHANNEL and KSPROPERTY_MEMBER_FLAG_BASICSUPPORT_UNIFORM, see [Exposing Multichannel Nodes](/windows-hardware/drivers/audio/exposing-multichannel-nodes) in the Windows Driver Kit (WDK) Audio documentation.

## -see-also

[**KSPROPERTY_BOUNDS_LONG**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_long)

[**KSPROPERTY_BOUNDS_LONGLONG**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_longlong)

[**KSPROPERTY_DESCRIPTION**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_description)

[**KSPROPERTY_ITEM**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item)

[**KSPROPERTY_MEMBERSLIST**](/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_memberslist)

[**KSPROPERTY_STEPPING_LONG**](/previous-versions/windows/hardware/drivers/dn936838(v=vs.85))

[**KSPROPERTY_STEPPING_LONGLONG**](/previous-versions/windows/hardware/drivers/dn936841(v=vs.85))
