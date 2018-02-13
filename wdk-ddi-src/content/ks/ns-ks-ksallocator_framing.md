---
UID: NS:ks.KSALLOCATOR_FRAMING
title: KSALLOCATOR_FRAMING
author: windows-driver-content
description: The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests.
old-location: stream\ksallocator_framing.htm
old-project: stream
ms.assetid: db96eccd-6747-458b-9a9e-ec909146f3fa
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSALLOCATOR_FRAMING, ks/KSALLOCATOR_FRAMING, stream.ksallocator_framing, PKSALLOCATOR_FRAMING, KSALLOCATOR_FRAMING structure [Streaming Media Devices], KSALLOCATOR_FRAMING, PKSALLOCATOR_FRAMING structure pointer [Streaming Media Devices], ks/PKSALLOCATOR_FRAMING, ks-struct_cc2d8d16-75d5-4ef4-b8de-63197e61424b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSALLOCATOR_FRAMING
product: Windows
targetos: Windows
req.typenames: "*PKSALLOCATOR_FRAMING, KSALLOCATOR_FRAMING"
---

# KSALLOCATOR_FRAMING structure


## -description


The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests.


## -syntax


````
typedef struct {
  union {
    ULONG OptionsFlags;
    ULONG RequirementsFlags;
  };
  ULONG PoolType;
  ULONG Frames;
  ULONG FrameSize;
  ULONG FileAlignment;
  ULONG Reserved;
} KSALLOCATOR_FRAMING, *PKSALLOCATOR_FRAMING;
````


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

A structure of type <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> that specifies kernel-mode allocation pool type.


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

<a href="..\ks\nf-ks-kscreateallocator.md">KsCreateAllocator</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSALLOCATOR_FRAMING structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

