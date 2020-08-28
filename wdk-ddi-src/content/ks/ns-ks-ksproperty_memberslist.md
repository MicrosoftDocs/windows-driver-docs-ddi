---
UID: NS:ks.__unnamed_struct_64
title: KSPROPERTY_MEMBERSLIST (ks.h)
description: The KSPROPERTY_MEMBERSLIST structure contains a list of legal values or ranges for a property.
old-location: stream\ksproperty_memberslist.htm
tech.root: stream
ms.assetid: 2354da98-8663-4758-add7-3ac4350f563c
ms.date: 04/23/2018
keywords: ["KSPROPERTY_MEMBERSLIST structure"]
ms.keywords: "*PKSPROPERTY_MEMBERSLIST, KSPROPERTY_MEMBERSLIST, KSPROPERTY_MEMBERSLIST structure [Streaming Media Devices], PKSPROPERTY_MEMBERSLIST, PKSPROPERTY_MEMBERSLIST structure pointer [Streaming Media Devices], ks-struct_44a818f7-bffd-4aa5-aa30-b6376c0593ca.xml, ks/KSPROPERTY_MEMBERSLIST, ks/PKSPROPERTY_MEMBERSLIST, stream.ksproperty_memberslist"
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
req.typenames: KSPROPERTY_MEMBERSLIST, *PKSPROPERTY_MEMBERSLIST
f1_keywords:
 - PKSPROPERTY_MEMBERSLIST
 - ks/PKSPROPERTY_MEMBERSLIST
 - KSPROPERTY_MEMBERSLIST
 - ks/KSPROPERTY_MEMBERSLIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPROPERTY_MEMBERSLIST
---

# KSPROPERTY_MEMBERSLIST structure


## -description

The KSPROPERTY_MEMBERSLIST structure contains a list of legal values or ranges for a property.

## -struct-fields

### -field MembersHeader

Indicates a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a> that specifies the size and type of information contained in the <b>Members</b> array.

### -field Members

Points to an array of entries that specify legal values or ranges for a property. Each entry describes a value or a set of a values.

## -remarks

The type of structures pointed to in the <b>Members</b> array depends on the value of <b>MembersHeader.MembersFlags</b>. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a> for details on possible flag values.  

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a> structure contains a pointer to an array of KSPROPERTY_MEMBERSLIST structures that specify valid range and value information for a property. In turn, a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item">KSPROPERTY_ITEM</a> structure contains a pointer to a KSPROPERTY_VALUES structure.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_long">KSPROPERTY_BOUNDS_LONG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_bounds_longlong">KSPROPERTY_BOUNDS_LONGLONG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_description">KSPROPERTY_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item">KSPROPERTY_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn936838(v=vs.85)">KSPROPERTY_STEPPING_LONG</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/dn936841(v=vs.85)">KSPROPERTY_STEPPING_LONGLONG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a>

