---
UID: NS:ks.__unnamed_struct_37
title: KSALLOCATOR_FRAMING (ks.h)
description: The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests.
old-location: stream\ksallocator_framing.htm
tech.root: stream
ms.date: 04/23/2018
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

# KSALLOCATOR_FRAMING structure


## -description

The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests.

## -struct-fields

### -field OptionsFlags

Specifies the allocator option flags specified during allocator creation for the connection point. The <b>OptionsFlags</b> member can contain one of the following values.

<table>
<tr>
<th>OptionsFlags</th>
<th>Description</th>
</tr>
<tr>
<td>
KSALLOCATOR_OPTIONF_COMPATIBLE

</td>
<td>
Indicates that the framing options of the allocator being created are compatible with the downstream allocator. This option is typically specified when an in-place modifier is assigned an allocator for copy buffers. If the filter is not required to modify a given frame, it may submit the frame to the downstream filter without allocating an additional frame from the downstream allocator when this option is specified.

</td>
</tr>
<tr>
<td>
KSALLOCATOR_OPTIONF_SYSTEM_MEMORY

</td>
<td>
Indicates that system memory should be used for allocations. When specified, the allocator must allocate memory from the pool as specified in the <b>PoolType</b> member. Otherwise, it is assumed that the sink provides a system address mapping to on-board RAM or other forms of storage on the device.

</td>
</tr>
</table>

### -field RequirementsFlags

A value of type ULONG that describes the allocator requirements for this connection point for query operations. The <b>RequirementsFlags</b> member can contain the following values.

<table>
<tr>
<th>Flag Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSALLOCATOR_REQUIREMENTF_INPLACE_MODIFIER

</td>
<td>
Indicates that the connection point can perform an in-place modification.

</td>
</tr>
<tr>
<td>
KSALLOCATOR_REQUIREMENTF_SYSTEM_MEMORY

</td>
<td>
Indicates that the connection point requires system memory for allocations. If this option is not set, it is assumed that the sink provides a system address space mapping to on-board RAM or other forms of storage on the device.

</td>
</tr>
<tr>
<td>
KSALLOCATOR_REQUIREMENTF_FRAME_INTEGRITY

</td>
<td>
Indicates that the connection point requires that downstream filters maintain the data integrity of specified frames.

</td>
</tr>
<tr>
<td>
KSALLOCATOR_REQUIREMENTF_MUST_ALLOCATE

</td>
<td>
Indicates that the connection point requires that it allocate any frames sent.

</td>
</tr>
<tr>
<td>
KSALLOCATOR_REQUIREMENTF_PREFERENCES_ONLY

</td>
<td>
Indicates that the Requirements flags are preferences only and the connection point is able to allocate frames that do not meet those specifications.

</td>
</tr>
</table>

### -field PoolType

A structure of type <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a> that specifies kernel-mode allocation pool type.

### -field Frames

Specifies the total number of allowable outstanding frames. Zero indicates that the filter has no requirement for this member.

### -field FrameSize

Specifies the total size of the frame, including prefix and postfix. Zero indicates that the filter has no requirement for this member.

### -field FileAlignment

A value of type ULONG that describes the byte alignment to use when allocating frames. The following table describes several possible alignment values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
FILE_BYTE_ALIGNMENT

</td>
<td>
1-byte alignment

</td>
</tr>
<tr>
<td>
FILE_WORD_ALIGNMENT

</td>
<td>
2-byte alignment

</td>
</tr>
<tr>
<td>
FILE_LONG_ALIGNMENT

</td>
<td>
4-byte alignment

</td>
</tr>
<tr>
<td>
FILE_32_BYTE_ALIGNMENT

</td>
<td>
32-byte alignment

</td>
</tr>
<tr>
<td>
FILE_64_BYTE_ALIGNMENT

</td>
<td>
64-byte alignment

</td>
</tr>
</table>

### -field FramePitch

### -field Reserved

Reserved for system use. Set to zero.

## -remarks

Use KSALLOCATOR_FRAMING to submit an allocator creation request to a handle of a sink by using IRP_MJ_CREATE.

When you specify a value for the <b>FileAlignment</b> member, the smallest allocation alignment is 1 byte (FILE_BYTE_ALIGNMENT). Software that functions as an allocation should support 4-byte alignment (FILE_LONG_ALIGNMENT), if possible.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscreateallocator">KsCreateAllocator</a>

