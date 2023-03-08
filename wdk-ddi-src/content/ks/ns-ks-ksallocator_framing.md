---
UID: NS:ks.KSALLOCATOR_FRAMING
title: KSALLOCATOR_FRAMING (ks.h)
description: The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests.
tech.root: stream
ms.date: 03/06/2023
keywords: ["KSALLOCATOR_FRAMING structure"]
ms.keywords: "*PKSALLOCATOR_FRAMING, KSALLOCATOR_FRAMING, KSALLOCATOR_FRAMING structure [Streaming Media Devices], PKSALLOCATOR_FRAMING, PKSALLOCATOR_FRAMING structure pointer [Streaming Media Devices], ks-struct_cc2d8d16-75d5-4ef4-b8de-63197e61424b.xml, ks/KSALLOCATOR_FRAMING, ks/PKSALLOCATOR_FRAMING, stream.ksallocator_framing"
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
req.typenames: KSALLOCATOR_FRAMING, *PKSALLOCATOR_FRAMING
f1_keywords:
 - PKSALLOCATOR_FRAMING
 - ks/PKSALLOCATOR_FRAMING
 - KSALLOCATOR_FRAMING
 - ks/KSALLOCATOR_FRAMING
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSALLOCATOR_FRAMING
 - KSALLOCATOR_FRAMING
---

## -description

The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests.

## -struct-fields

### -field OptionsFlags

Specifies the allocator option flags specified during allocator creation for the connection point. The **OptionsFlags** member can contain one of the following values.

| OptionsFlags | Description |
|---|---|
| KSALLOCATOR_OPTIONF_COMPATIBLE | Indicates that the framing options of the allocator being created are compatible with the downstream allocator. This option is typically specified when an in-place modifier is assigned an allocator for copy buffers. If the filter is not required to modify a given frame, it may submit the frame to the downstream filter without allocating an additional frame from the downstream allocator when this option is specified. |
| KSALLOCATOR_OPTIONF_SYSTEM_MEMORY | Indicates that system memory should be used for allocations. When specified, the allocator must allocate memory from the pool as specified in the **PoolType** member. Otherwise, it is assumed that the sink provides a system address mapping to on-board RAM or other forms of storage on the device. |

### -field RequirementsFlags

A value of type ULONG that describes the allocator requirements for this connection point for query operations. The **RequirementsFlags** member can contain the following values.

| Flag Value | Description |
|---|---|
| KSALLOCATOR_REQUIREMENTF_INPLACE_MODIFIER | Indicates that the connection point can perform an in-place modification. |
| KSALLOCATOR_REQUIREMENTF_SYSTEM_MEMORY | Indicates that the connection point requires system memory for allocations. If this option is not set, it is assumed that the sink provides a system address space mapping to on-board RAM or other forms of storage on the device. |
| KSALLOCATOR_REQUIREMENTF_FRAME_INTEGRITY | Indicates that the connection point requires that downstream filters maintain the data integrity of specified frames. |
| KSALLOCATOR_REQUIREMENTF_MUST_ALLOCATE | Indicates that the connection point requires that it allocate any frames sent. |
| KSALLOCATOR_REQUIREMENTF_PREFERENCES_ONLY | Indicates that the Requirements flags are preferences only and the connection point is able to allocate frames that do not meet those specifications. |

### -field PoolType

A structure of type [POOL_TYPE](/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type) that specifies kernel-mode allocation pool type.

### -field Frames

Specifies the total number of allowable outstanding frames. Zero indicates that the filter has no requirement for this member.

### -field FrameSize

Specifies the total size of the frame, including prefix and postfix. Zero indicates that the filter has no requirement for this member.

### -field FileAlignment

A value of type ULONG that describes the byte alignment to use when allocating frames. The following table describes several possible alignment values.

| Value | Description |
|---|---|
| FILE_BYTE_ALIGNMENT | 1-byte alignment |
| FILE_WORD_ALIGNMENT | 2-byte alignment |
| FILE_LONG_ALIGNMENT | 4-byte alignment |
| FILE_32_BYTE_ALIGNMENT | 32-byte alignment |
| FILE_64_BYTE_ALIGNMENT | 64-byte alignment |

### -field FramePitch

### -field Reserved

Reserved for system use. Set to zero.

## -remarks

Use KSALLOCATOR_FRAMING to submit an allocator creation request to a handle of a sink by using IRP_MJ_CREATE.

When you specify a value for the **FileAlignment** member, the smallest allocation alignment is 1 byte (FILE_BYTE_ALIGNMENT). Software that functions as an allocation should support 4-byte alignment (FILE_LONG_ALIGNMENT), if possible.

## -see-also

[KsCreateAllocator](/windows-hardware/drivers/ddi/ks/nf-ks-kscreateallocator)
