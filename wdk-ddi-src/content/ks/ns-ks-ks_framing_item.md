---
UID: NS:ks.KS_FRAMING_ITEM
title: KS_FRAMING_ITEM (ks.h)
description: The KS_FRAMING_ITEM structure is used to declare allocator requirements on a kernel-mode pin.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KS_FRAMING_ITEM structure"]
ms.keywords: "*PKS_FRAMING_ITEM, KSALLOCATOR_FLAG_CAN_ALLOCATE, KSALLOCATOR_FLAG_DEVICE_SPECIFIC, KSALLOCATOR_FLAG_INSIST_ON_FRAMESIZE_RATIO, KSALLOCATOR_FLAG_PARTIAL_READ_SUPPORT, KSALLOCATOR_REQUIREMENTF_PREFERENCES_ONLY, KS_FRAMING_ITEM, KS_FRAMING_ITEM structure [Streaming Media Devices], PKS_FRAMING_ITEM, PKS_FRAMING_ITEM structure pointer [Streaming Media Devices], ks-struct_8ddb4478-636f-4cd4-b4c1-663a20070cef.xml, ks/KS_FRAMING_ITEM, ks/PKS_FRAMING_ITEM, stream.ks_framing_item"
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
req.typenames: KS_FRAMING_ITEM, *PKS_FRAMING_ITEM
f1_keywords:
 - PKS_FRAMING_ITEM
 - ks/PKS_FRAMING_ITEM
 - KS_FRAMING_ITEM
 - ks/KS_FRAMING_ITEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKS_FRAMING_ITEM
 - KS_FRAMING_ITEM
---

## -description

The **KS_FRAMING_ITEM** structure is used to declare allocator requirements on a kernel-mode pin.

## -struct-fields

### -field MemoryType

Specifies the type of memory used for buffers and data frames. There is a partial correspondence between this member and the **PoolType** member in the [**KSALLOCATOR_FRAMING**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing) structure. The two members differ in that **PoolType** allows only paged or nonpaged pool. **MemoryType** can have any of the values listed in the following table.

| Value | Description |
|---|---|
| KSMEMORY_TYPE_WILDCARD / KSMEMORY_TYPE_DONT_CARE / KSTYPE_DONT_CARE | Indicates memory allocation can be any type of memory. |
| KSMEMORY_TYPE_SYSTEM | Indicates memory allocation must be system memory. |
| KSMEMORY_TYPE_USER | Indicates memory allocation must be user-mode memory. |
| KSMEMORY_TYPE_KERNEL_PAGED | Indicates memory allocation must be kernel paged memory. This corresponds to the **PoolType** member of the [**KSALLOCATOR_FRAMING**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing) structure set to **PagedPool** and the **RequirementsFlags** member of this structure set to SYSTEM_MEMORY. |
| KSMEMORY_TYPE_KERNEL_NONPAGED | Indicates memory allocation must be kernel nonpaged memory. This corresponds to the **PoolType** member of the [**KSALLOCATOR_FRAMING**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing) structure set to **NonPagedPool** and the **RequirementsFlags** member of this structure set to SYSTEM_MEMORY. |
| KSMEMORY_TYPE_DEVICE_UNKNOWN | Indicates device memory allocation type is not specified. |

### -field BusType

Specifies the physical bus accessing the physical memory specified by *MemoryType*. Use this field to determine a compatible memory type based on the bus that is used for the connection medium. This distinction is crucial when a pin exposes different memory types based on the connection medium. **BusType** can have any of the values listed in the following table.

| Type | Description |
|---|---|
| GUID_BUS_TYPE_PCI | Peripheral component interconnect bus. |
| GUID_BUS_TYPE_USB | Universal serial bus. |
| GUID_BUS_TYPE_1394 | IEEE 1394 serial bus. |
| GUID_BUS_TYPE_AVC | Audio/video control bus. |
| GUID_61883_CLASS | 61883 protocol bus. |

### -field MemoryFlags

Specifies that the connection point is responsible for frame allocation. Should be set to KSALLOCATOR_REQUIREMENTF_MUST_ALLOCATE.

### -field BusFlags

Not used.

### -field Flags

Similar to the **OptionsFlags** and **RequirementsFlags** union in the [**KSALLOCATOR_FRAMING**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing) structure, with the addition of the flags that add support for pipes.

### -field Frames

Specifies the total number of allowable outstanding frames. Corresponds to the **Frames** member of the [**KSALLOCATOR_FRAMING**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing) structure.

### -field FileAlignment

Requirement for frame alignment. Corresponds to the **FileAlignment** member of the [**KSALLOCATOR_FRAMING**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing) structure.

### -field FramePitch

Defines the **LONG** member **FramePitch**.

### -field MemoryTypeWeight

A value of type **ULONG** that specifies the pin-wide weight of this memory type.

### -field PhysicalRange

A structure of type [**KS_FRAMING_RANGE**](/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range) that specifies the physical limit of frame sizes.

### -field FramingRange

A structure of type [**KS_FRAMING_RANGE_WEIGHTED**](/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range_weighted) that specifies the optimal range of frame sizes.

## -remarks

Do not set KSALLOCATOR_FLAG_CAN_ALLOCATE to indicate memory addressing capability. A filter might be able to access the device-specific memory over a device-specific bus by referencing the memory address on this bus, and yet not support the protocol to allocate this device-specific memory.

Each [**KSALLOCATOR_FRAMING_EX**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing_ex) instance contains one or more framing items.

## -see-also

[**KSALLOCATOR_FRAMING**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing)

[**KSALLOCATOR_FRAMING_EX**](/windows-hardware/drivers/ddi/ks/ns-ks-ksallocator_framing_ex)

[**KS_COMPRESSION**](/windows-hardware/drivers/ddi/ks/ns-ks-ks_compression)

[**KS_FRAMING_RANGE**](/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range)

[**KS_FRAMING_RANGE_WEIGHTED**](/windows-hardware/drivers/ddi/ks/ns-ks-ks_framing_range_weighted)
