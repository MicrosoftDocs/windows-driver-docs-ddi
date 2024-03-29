---
UID: NS:ks.KSALLOCATOR_FRAMING_EX
title: KSALLOCATOR_FRAMING_EX (ks.h)
description: The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter.
old-location: stream\ksallocator_framing_ex.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSALLOCATOR_FRAMING_EX structure"]
ms.keywords: "*PKSALLOCATOR_FRAMING_EX, KSALLOCATOR_FRAMING_EX, KSALLOCATOR_FRAMING_EX structure [Streaming Media Devices], PKSALLOCATOR_FRAMING_EX, PKSALLOCATOR_FRAMING_EX structure pointer [Streaming Media Devices], ks-struct_d2aa8aab-1778-4383-b524-d52e4dd6c4c2.xml, ks/KSALLOCATOR_FRAMING_EX, ks/PKSALLOCATOR_FRAMING_EX, stream.ksallocator_framing_ex"
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
req.typenames: KSALLOCATOR_FRAMING_EX, *PKSALLOCATOR_FRAMING_EX
f1_keywords:
 - PKSALLOCATOR_FRAMING_EX
 - ks/PKSALLOCATOR_FRAMING_EX
 - KSALLOCATOR_FRAMING_EX
 - ks/KSALLOCATOR_FRAMING_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSALLOCATOR_FRAMING_EX
 - KSALLOCATOR_FRAMING_EX
---

# KSALLOCATOR_FRAMING_EX structure


## -description

The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter.

## -struct-fields

### -field CountItems

Specifies the number of framing items that are present in the **FramingItem** array.

### -field PinFlags

Reserved, set to zero.

### -field OutputCompression

Points to a structure of type [KS_COMPRESSION](./ns-ks-ks_compression.md) that defines the frame ratio for transforms that change the size of a frame.

### -field PinWeight

This pin framing's weight graph-wide. Reserved, set to zero.

### -field FramingItem

An array of [KS_FRAMING_ITEM](./ns-ks-ks_framing_item.md) structures specifying the actual framing items.

## -remarks

A minidriver can also use DECLARE_SIMPLE_FRAMING_EX to declare an extended framing structure in line with the original structure. This macro is defined in *Ks.h* as follows:

```cpp
#define DECLARE_SIMPLE_FRAMING_EX(FramingExName, MemoryType, Flags, Frames, Alignment, MinFrameSize, MaxFrameSize) const KSALLOCATOR_FRAMING_EX FramingExName
```

DECLARE_SIMPLE_FRAMING_EX declares a KSALLOCATOR_FRAMING_EX structure called **FramingExName** with the specified memory type (often either STATIC_KS_TYPE_DONT_CARE or one of the kernel paged or nonpaged GUIDs). The **Frames** and **Alignment** fields of the macro correspond to the [KSALLOCATOR_FRAMING](./ns-ks-ksallocator_framing.md). **MinFrameSize** and **MaxFrameSize** ensure that frames are within a specific size range. Flags corresponds to the **OptionsFlags** and **RequirementsFlags** in **KSALLOCATOR_FRAMING**.

## -see-also

[KSALLOCATOR_FRAMING](./ns-ks-ksallocator_framing.md)

[KS_COMPRESSION](./ns-ks-ks_compression.md)

[KS_FRAMING_ITEM](./ns-ks-ks_framing_item.md)

[KS_FRAMING_RANGE](./ns-ks-ks_framing_range.md)

[KS_FRAMING_RANGE_WEIGHTED](./ns-ks-ks_framing_range_weighted.md)

