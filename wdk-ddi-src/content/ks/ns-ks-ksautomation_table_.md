---
UID: NS:ks.KSAUTOMATION_TABLE_
title: KSAUTOMATION_TABLE_ (ks.h)
description: The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events.
old-location: stream\ksautomation_table.htm
tech.root: stream
ms.assetid: 76ab776d-0921-4fdb-9646-2cb97a582f6e
ms.date: 04/23/2018
ms.keywords: "*PKSAUTOMATION_TABLE, KSAUTOMATION_TABLE, KSAUTOMATION_TABLE structure [Streaming Media Devices], KSAUTOMATION_TABLE_, PKSAUTOMATION_TABLE, PKSAUTOMATION_TABLE structure pointer [Streaming Media Devices], avstruct_7389df5c-d86a-43b2-9daf-d0e1e8a2dfbe.xml, ks/KSAUTOMATION_TABLE, ks/PKSAUTOMATION_TABLE, stream.ksautomation_table"
ms.topic: struct
f1_keywords:
 - "ks/KSAUTOMATION_TABLE"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSAUTOMATION_TABLE
product:
- Windows
targetos: Windows
req.typenames: KSAUTOMATION_TABLE, *PKSAUTOMATION_TABLE
---

# KSAUTOMATION_TABLE_ structure

## -description

The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events.

## -struct-fields

### -field PropertySetsCount

This member specifies the number of property sets in this automation table.

### -field PropertyItemSize

This member specifies size in bytes of property items in this table.

### -field PropertySets

A pointer to an array of [KSPROPERTY_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_set) objects (**PropertySetsCount** in length) defining the property sets in this automation table.  Each set contains a specific number of items of size **PropertyItemSize**.

### -field MethodSetsCount

This member specifies the number of method sets in this automation table.

### -field MethodItemSize

This member specifies the size in bytes of method items in this table.

### -field MethodSets

An array of [KSMETHOD_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmethod_set) objects (**MethodSetsCount** in length) defining the method sets in this automation table.  Each set has a specific number of items in it of size **MethodItemSize**.

### -field EventSetsCount

This member specifies the number of event sets in this automation table.

### -field EventItemSize

This member specifies the size in bytes of event items in this table.

### -field EventSets

An array of [KSEVENT_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksevent_set) objects (**EventSetsCount** in length) defining the event sets in this automation table.  Each set has a specific number of items in it of size **EventItemSize**.

### -field Alignment

Reserved for internal use by AVStream. Minidrivers should not manipulate this member.

## -remarks

Note that each object (pin, filter, topology node) should define an automation table. Minidrivers can use macros defined in *Ks.h* to define automation tables and the arrays they contain:

- DEFINE_KSAUTOMATION_TABLE

- DEFINE_KSAUTOMATION_PROPERTIES

- DEFINE_KSAUTOMATION_METHODS

- DEFINE_KSAUTOMATION_EVENTS

To specify an automation table containing an empty property array, event array, or method array:

- DEFINE_KSAUTOMATION_PROPERTIES_NULL

- DEFINE_KSAUTOMATION_METHODS_NULL

- DEFINE_KSAUTOMATION_EVENTS_NULL

For example:

```cpp
DEFINE_KSAUTOMATION_TABLE (MyAutomationTable) {
    DEFINE_KSAUTOMATION_PROPERTIES (MyPropertyTable),
    DEFINE_KSAUTOMATION_METHODS (MyMethodTable),
    DEFINE_KSAUTOMATION_EVENTS (MyEventTable)
    };
```

## -see-also

[KSEVENT_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksevent_item)

[KSEVENT_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksevent_set)

[KSMETHOD_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmethod_item)

[KSMETHOD_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksmethod_set)

[KSPROPERTY_ITEM](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_item)

[KSPROPERTY_SET](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksproperty_set)
